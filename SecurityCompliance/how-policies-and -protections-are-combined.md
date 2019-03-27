---
title: Come vengono combinati i criteri e le protezioni quando la posta viene contrassegnata con un contrassegno rosso
description: Quali criteri si applicano e quali azioni eseguire, quando la posta elettronica è contrassegnata da malware, posta indesiderata, posta indesiderata elevata, phishing e bulk da EOP e/o ATP.
keywords: sicurezza, malware, Microsoft 365, M365, Centro sicurezza, ATP, Windows Defender ATP, Office 365 ATP, Azure ATP
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 03/26/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 7aa0f89eed379273cb069cd65c083749a9552e91
ms.sourcegitcommit: a79eb9907759d4cd849c3f948695a9ff890b19bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2019
ms.locfileid: "30926469"
---
# <a name="what-policy-applies-when-multiple-protection-methods-and-detection-scans-run-on-your-email"></a>Quali criteri si applicano quando più metodi di protezione e analisi di rilevamento vengono eseguiti nel messaggio di posta elettronica

Potenzialmente, la posta in arrivo può essere contrassegnata da più forme di protezione (ad esempio, sia EOP *che* ATP) e più analisi di rilevamento (come posta indesiderata *e* phishing). Ciò è possibile perché esistono criteri di anti-phishing ATP per i clienti ATP e criteri anti-phishing di EOP per i clienti di EOP. In questo modo, ad esempio, il messaggio può esplorare più analisi di rilevamento per malware, phishing e rappresentazione utente. Date tutte queste attività, è possibile che si verifichi una certa confusione sui criteri applicati.

In generale, il criterio applicato a un messaggio viene identificato nell'intestazione **X-Forefront-antispam-report** nella proprietà **Cat (categoria)** . Se si dispone di più criteri di anti-phishing, verrà applicato quello con la priorità più alta.

I criteri riportati di seguito si applicano a _tutte le organizzazioni_.

|Priority |Criteri  |Categoria  |Dove gestito |
|---------|---------|---------|---------|
|1     | Malware      | MALW      | Criteri anti-malware   |
|2     | Phishing     | PHSH     | Configurare i criteri di filtro della posta indesiderata     |
|3     | Alta probabilità di posta indesiderata      | HSPM        | Configurare i criteri di filtro della posta indesiderata        |
|4     | Spoofing        | SPOOFING        | Criteri di anti-phishing, spoofing Intelligence        |
|5     | Posta indesiderata         | SPM         | Configurare i criteri di filtro della posta indesiderata         |
|6     | Invio in blocco         | BULK        | Configurare i criteri di filtro della posta indesiderata         |

Inoltre, questi criteri si applicano alle _organizzazioni con ATP_.

|Priority |Criteri  |Categoria  |Dove gestito |
|---------|---------|---------|---------|
|7     | Rappresentazione del dominio         | DIMP         | Impostare i criteri di anti-phishing e l’anti-phishing di Office 365 ATP         |
|8     | Rappresentazione utente        | UIMP         | Impostare i criteri di anti-phishing e l’anti-phishing di Office 365 ATP          |

Ad esempio, se si dispone di due criteri:

|Criteri  |Priority  |Rappresentazione del dominio/utente  |Anti-spoofing  |
|---------|---------|---------|---------|
|A     | 1        | Attivato        |Disattivato         |
|B     | 2        | Disattivato        | Attivato        |

Se un messaggio viene identificato come rappresentazione e _spoofing_ _dell'utente_ (vedere anti-spoofing nella tabella precedente) e lo stesso insieme di utenti con ambito ai criteri a ha come ambito il criterio B, il messaggio viene contrassegnato e considerato come _spoof_, ma non l'azione viene applicata dopo che l'antispoofing è disattivata e perché **spoof viene eseguito con una priorità più alta (4) rispetto alla rappresentazione dell'utente (8)**.

Per applicare altri tipi di criteri di phishing, è necessario modificare le impostazioni a cui si applicano i vari criteri.



