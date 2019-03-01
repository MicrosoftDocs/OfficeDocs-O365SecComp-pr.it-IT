---
title: Creazione impronta digitale documenti
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 1e0c579c-26e0-462a-a1b0-d7506dfe05fa
description: Gli Information Worker dell'organizzazione gestiscono numerosi tipi di informazioni riservate durante una giornata tipica. L'impronta digitale del documento semplifica la protezione delle informazioni identificando i moduli standard utilizzati nell'organizzazione. In questo argomento vengono descritti i concetti che stanno alla base dell'impronta digitale del documento e come crearne uno tramite PowerShell.
ms.openlocfilehash: 20b9f59902c52d347e7c439cb6f380ee9fd4a30e
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341287"
---
# <a name="document-fingerprinting"></a>Creazione impronta digitale documenti

Gli Information Worker dell'organizzazione gestiscono numerosi tipi di informazioni riservate durante una giornata tipica. Nel centro sicurezza &amp; e conformità, le impronte digitali dei documenti facilitano la protezione delle informazioni identificando i moduli standard utilizzati nell'organizzazione. In questo argomento vengono descritti i concetti che stanno alla base dell'impronta digitale del documento e come crearne uno tramite PowerShell.
  
## <a name="basic-scenario-for-document-fingerprinting"></a>Scenario di base per la creazione impronta digitale documenti

L'impronta digitale del documento è una funzionalità di prevenzione della perdita di dati (DLP) che converte un modulo standard in un tipo di informazioni riservate, che è possibile utilizzare nelle regole dei criteri DLP. Ad esempio, è possibile creare un'impronta digitale del documento in base a un modello di brevetto vuoto e quindi creare un criterio DLP che rileva e blocca tutti i modelli di brevetto in uscita con contenuti sensibili inseriti. Facoltativamente, è possibile impostare suggerimenti per i [criteri](use-notifications-and-policy-tips.md) per segnalare ai mittenti che potrebbero inviare informazioni riservate e il mittente deve verificare che i destinatari siano qualificati per la ricezione dei brevetti. Questo processo è compatibile con i moduli basati su testo utilizzati nell'organizzazione. Sono disponibili ulteriori esempi di moduli che è possibile caricare: 
  
- Moduli governativi
    
- Moduli di conformità Health Insurance Portability and Accountability Act (HIPAA)
    
- Moduli di informazioni dei dipendenti per i reparti delle risorse umane
    
- Moduli personalizzati creati specificamente per l'organizzazione
    
Idealmente, l'organizzazione dispone già di una prassi aziendale consolidata dell'utilizzo di alcuni moduli per la trasmissione di informazioni riservate. Dopo aver caricato una maschera vuota per essere convertita in un'impronta digitale del documento e aver configurato un criterio corrispondente, il DLP rileva tutti i documenti nella posta in uscita che corrispondono a tale impronta digitale.
  
## <a name="how-document-fingerprinting-works"></a>Funzionamento dell'impronta digitale del documento

Probabilmente è già stato indovinato che i documenti non dispongono di impronte digitali effettive, ma il nome aiuta a spiegare la caratteristica. Nello stesso modo in cui le impronte digitali di una persona hanno modelli univoci, i documenti dispongono di modelli di parole univoci. Quando si carica un file, DLP identifica il modello di parola univoco nel documento, crea un'impronta digitale del documento in base a tale modello e utilizza tale impronta digitale per rilevare i documenti in uscita che contengono lo stesso modello. Questo è il motivo per cui il caricamento di una maschera o di un modello crea il tipo più efficace di impronte digitali del documento. Tutti gli utenti che compilano un modulo utilizzano lo stesso set di parole originale e quindi aggiungono le parole al documento. Fintanto che il documento in uscita non è protetto da password e contiene tutto il testo del modulo originale, DLP è in grado di determinare se il documento corrisponde all'impronta digitale del documento.
  
Il seguente esempio mostra cosa accade si crea un'impronta digitale del documento in base al modello di brevetto. È comunque possibile usare qualsiasi modello per la creazione di un'impronta digitale del documento.
  
**Esempio di un documento di brevetto corrispondente a un'impronta digitale del documento di un modello di brevetto**

![Document_Fingerprinting_diagram. png](media/Document_Fingerprinting_diagram.png)
  
Il modello di brevetto contiene i campi vuoti "titolo brevetto", "inventori" e "Descrizione" e descrizioni per ognuno di questi campi, ovvero il modello di parola. Quando si carica il modello di brevetto originale, si trova in uno dei tipi di file supportati e in testo normale. DLP converte questo modello di parola in un'impronta digitale del documento, che è un piccolo file XML Unicode contenente un valore hash univoco che rappresenta il testo originale e l'impronta digitale viene salvata come classificazione dei dati in Active Directory. (Come misura di sicurezza, il documento originale non è archiviato nel servizio, solo il valore hash è archiviato e il documento originale non può essere ricostruito dal valore hash). L'impronta digitale del brevetto diventa quindi un tipo di informazioni riservate che è possibile associare a un criterio DLP. Dopo aver associato l'impronta digitale a un criterio DLP, DLP rileva eventuali messaggi di posta elettronica in uscita contenenti documenti che corrispondono all'impronta digitale del brevetto e li gestisce in base ai criteri dell'organizzazione. 

Ad esempio, potrebbe essere necessario configurare un criterio DLP che impedisca ai dipendenti regolari di inviare messaggi in uscita contenenti brevetti. DLP utilizzerà l'impronta digitale del brevetto per rilevare i brevetti e bloccare tali messaggi di posta elettronica. In alternativa, è possibile lasciare che il proprio reparto legale sia in grado di inviare brevetti ad altre organizzazioni perché ha bisogno di questo tipo di attività. È possibile consentire a determinati reparti di inviare informazioni riservate creando eccezioni per i reparti del criterio DLP oppure è possibile consentire loro di ignorare un suggerimento per i criteri con una giustificazione aziendale.
  
### <a name="supported-file-types"></a>Tipi di file supportati

L'impronta digitale del documento supporta gli stessi tipi di file supportati nelle regole del flusso di posta (note anche come regole di trasporto). Per un elenco dei tipi di file supportati, vedere [tipi di file supportati per l'ispezione del contenuto delle regole del flusso di posta](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). Una breve nota sui tipi di file: né le regole del flusso di posta né le impronte digitali del documento supportano il tipo di file. dotx, che può essere confusionario perché si tratta di un file modello in Word. Quando viene visualizzata la parola "modello" in questo e altri argomenti relativi alle impronte digitali dei documenti, si fa riferimento a un documento definito come modulo standard, non al tipo di file modello.
  
#### <a name="limitations-of-document-fingerprinting"></a>Limitazioni della creazione dell'impronta digitale del documento

L'impronta digitale del documento non rileva informazioni riservate nei casi seguenti:
  
- File protetti da password
    
- File che contengono solo immagini
    
- Documenti che non contengono tutto il testo del modulo originale usato per la creazione dell'impronta digitale del documento
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>Utilizzo di PowerShell per creare un pacchetto di regole di classificazione basato sull'impronta digitale dei documenti

Si noti che è possibile creare un'impronta digitale del documento solo tramite PowerShell nel centro &amp; sicurezza e conformità. Per la connessione, vedere [Connect to Office 365 Security _AMP_ Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

DLP utilizza pacchetti di regole di classificazione per rilevare contenuti sensibili. Per creare un pacchetto di regole di classificazione in base a un'impronta digitale del documento, utilizzare i cmdlet **New-DlpFingerprint** e **New-DlpSensitiveInformationType** . Poiché i risultati di **New-DlpFingerprint** non sono archiviati all'esterno della regola di classificazione dei dati, vengono sempre eseguiti **New-DlpFingerprint** e **New-DlpSensitiveInformationType** o **set-DlpSensitiveInformationType** nello stesso Sessione di PowerShell. Nell'esempio seguente viene creata una nuova impronta digitale del documento basata sul file C:\My C:\documenti\contoso Employee template. docx. È possibile archiviare la nuova impronta digitale come variabile, in modo da poterla utilizzare con il cmdlet **New-DlpSensitiveInformationType** nella stessa sessione di PowerShell. 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

A questo punto, passiamo alla creazione di una nuova regola di classificazione dati denominata "Contoso Employee Confidential" che utilizza l'impronta digitale del documento del file C:\Documenti\Contoso Customer Information Form.docx.
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

È ora possibile utilizzare il cmdlet **Get-DlpSensitiveInformationType** per trovare tutti i pacchetti di regole di classificazione dei dati DLP e, in questo esempio, "contoso Customer Confidential" fa parte dell'elenco dei pacchetti di regole di classificazione dei dati. 
  
Infine, aggiungere il pacchetto di regole di classificazione dei dati "contoso Customer Confidential" a un criterio DLP &amp; nel centro sicurezza e conformità. In questo esempio viene aggiunta una regola a un criterio DLP esistente denominato "ConfidentialPolicy".

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

È inoltre possibile utilizzare il pacchetto di regole di classificazione dei dati nelle regola del flusso di posta in Exchange Online, come illustrato nell'esempio seguente. Per eseguire questo comando, è innanzitutto necessario [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Si noti inoltre che richiede tempo affinché il pacchetto di regole venga sincronizzato dal &amp; centro conformità di sicurezza all'interfaccia di amministrazione di Exchange.
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

DLP rileva ora i documenti che corrispondono all'impronta digitale del documento contoso Customer form. docx.
  
Per informazioni sulla sintassi e sui parametri, vedere:

- [New-DlpFingerprint](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [New-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
