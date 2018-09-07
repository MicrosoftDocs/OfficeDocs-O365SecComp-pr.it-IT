---
title: Creazione impronta digitale documenti
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 1e0c579c-26e0-462a-a1b0-d7506dfe05fa
description: Gli Information Worker all'interno dell'organizzazione di gestire diversi tipi di informazioni riservate durante un giorno tipico. Creazione impronta digitale documenti semplifica proteggere queste informazioni identificando moduli standard utilizzati in tutta l'organizzazione. In questo argomento vengono descritti i concetti relativi all'impronta digitale del documento e su come creare una tramite PowerShell.
ms.openlocfilehash: d73b769e7a014f2642a0fcd66cc6a500c68c46c3
ms.sourcegitcommit: 4be502d1fc6cbaef4c72d599758d51efe3a173c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "23867498"
---
# <a name="document-fingerprinting"></a>Creazione impronta digitale documenti

Gli Information Worker all'interno dell'organizzazione di gestire diversi tipi di informazioni riservate durante un giorno tipico. In sicurezza &amp; centro conformità, impronta digitale del documento è più semplice consente di proteggere queste informazioni identificando moduli standard utilizzati in tutta l'organizzazione. In questo argomento vengono descritti i concetti relativi all'impronta digitale del documento e su come creare una tramite PowerShell.
  
## <a name="basic-scenario-for-document-fingerprinting"></a>Scenario di base per la creazione impronta digitale documenti

Creazione impronta digitale documenti è una funzionalità di prevenzione della perdita di dati (DLP) che converte un modulo standard in un tipo di informazioni riservate, è possibile utilizzare le regole dei criteri DLP. Ad esempio, si può creare impronta digitale del documento basata su un modello di brevetto vuoto e quindi creare un criterio DLP che consente di rilevare e Blocca tutti i modelli di brevetto in uscita con contenuto riservato compilati. Facoltativamente, è possibile impostare i [suggerimenti sui criteri](use-notifications-and-policy-tips.md) per notificare mittenti potrebbe essere l'invio di informazioni riservate che il mittente deve verificare che i destinatari sono completi per la ricezione di brevetti. Questo processo funziona con qualsiasi testo basata su moduli utilizzati nell'organizzazione. Ulteriori esempi di moduli che è possibile caricare includono: 
  
- Moduli governativi
    
- Moduli di conformità Health Insurance Portability and Accountability Act (HIPAA)
    
- Moduli di informazioni dei dipendenti per i reparti delle risorse umane
    
- Moduli personalizzati creati specificamente per l'organizzazione
    
In teoria, l'organizzazione ha già un'esercitazione commerciale dell'utilizzo di determinati moduli per trasmettere informazioni riservate. Dopo aver caricato un modulo vuoto da convertire in un'impronta digitale del documento e configurare un criterio corrispondente, il DLP rileva i documenti nella posta in uscita che soddisfano tale impronta digitale.
  
## <a name="how-document-fingerprinting-works"></a>Funzionamento dell'impronta digitale del documento

Probabile che sia già stato individuata che non dispongono di effettivo delle impronte digitali dei documenti, ma il nome consente di illustrare la funzionalità. Allo stesso modo che le impronte digitali di una persona sono schemi univoci, i documenti hanno modelli di word univoco. Quando si carica un file, DLP identifica il formato di word univoco nel documento, consente di creare un'impronta digitale documenti basata su tale modello e utilizza tale impronta digitale del documento per rilevare i documenti in uscita che contiene lo stesso modello. Il motivo per il caricamento di un modulo o modello consente di creare il tipo più efficace dell'impronta digitale del documento. Tutti gli utenti compila un modulo utilizza lo stesso insieme di parole originale e quindi i propri parole vengono aggiunte al documento. Purché il documento in uscita non è protetto da password e contiene tutto il testo del modulo originale, DLP può determinare se il documento corrisponde l'impronta digitale del documento.
  
Il seguente esempio mostra cosa accade si crea un'impronta digitale del documento in base al modello di brevetto. È comunque possibile usare qualsiasi modello per la creazione di un'impronta digitale del documento.
  
**Esempio di un documento di brevetto corrispondente a un'impronta digitale del documento di un modello di brevetto**

![Document_Fingerprinting_diagram.PNG](media/Document_Fingerprinting_diagram.png)
  
Il modello di brevetto contiene campi vuoti "Brevetto title", "Inventori," e "Descrizione" e le descrizioni per ognuno di tali campi, che è il modello di word. Quando si carica il modello di brevetto originale, è in uno dei tipi di file supportati in testo normale. Converte DLP questo formato di word in un'impronta digitale del documento, che corrisponde a un file XML di Unicode piccoli file che contiene un valore hash univoco che rappresenta il testo originale e l'impronta digitale viene salvato come una classificazione dei dati di Active Directory. (Come misura di protezione, il servizio non viene archiviato il documento originale stesso; solo il valore hash viene archiviato e il documento originale non può essere ricostruito dal valore hash.) L'impronta digitale brevetto diventa un tipo di informazioni riservate che è possibile associare a un criterio DLP. Dopo aver associato l'impronta digitale a un criterio DLP, DLP rileva eventuali messaggi di posta elettronica in uscita che contengono i documenti che soddisfano l'impronta digitale brevetto e si occupa di essi in base ai criteri dell'organizzazione. 

Ad esempio, è possibile impostare un criterio DLP che impedisce l'invio di messaggi in uscita contenenti brevetti ai dipendenti regolari. DLP utilizzerà l'impronta digitale brevetto per rilevare brevetti e bloccare i messaggi di posta elettronica. In alternativa, è possibile consentire il proprio ufficio legale per poter inviare brevetti ad altre organizzazioni, in quanto presenta un business necessari per eseguire questa operazione. È possibile consentire reparti specifici per l'invio di informazioni riservate mediante la creazione di eccezioni per i reparti nel criterio DLP oppure è possibile consentire loro di eseguire l'override di un suggerimento per il criterio con una giustificazione aziendale.
  
### <a name="supported-file-types"></a>Tipi di file supportati

Creazione impronta digitale documenti supporta gli stessi tipi di file supportati nelle regole di trasporto. Per un elenco di tipi di file supportati, vedere [tipi di file supportati per esaminare le mail flow regole](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). Una nota rapida sui tipi di file: le regole di trasporto né impronta digitale del documento supporta il tipo di file con estensione dotx, che può risultare complessa perché è un file di modello di Word. Quando viene visualizzata la parola "modello" in questo e altri argomenti impronta digitale del documento, fa riferimento a un documento che è stato stabilito come un modulo standard, non il tipo di file di modello.
  
#### <a name="limitations-of-document-fingerprinting"></a>Limitazioni della creazione dell'impronta digitale del documento

Creazione impronta digitale documenti non rileva informazioni riservate nei seguenti casi:
  
- File protetti da password
    
- File che contengono solo immagini
    
- Documenti che non contengono tutto il testo del modulo originale usato per la creazione dell'impronta digitale del documento
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>Utilizzare PowerShell per creare un pacchetto di regole di classificazione basato su impronta digitale del documento

Si noti che attualmente è possibile creare un'impronta digitale del documento solo tramite PowerShell nella protezione &amp; centro conformità. Per la connessione, vedere [Connect to Office 365 Security & PowerShell centro conformità](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

Pacchetti di regole di classificazione vengono utilizzate da DLP per rilevare contenuti sensibili. Per creare un pacchetto di regole di classificazione basato su un'impronta digitale del documento, utilizzare il cmdlet **New-DlpFingerprint** e **New-DlpSensitiveInformationType** . Poiché i risultati di **New-DlpFingerprint** non vengono memorizzati di fuori la regola di classificazione dei dati, è sempre eseguire **New-DlpFingerprint** e **New-DlpSensitiveInformationType** o **Set-DlpSensitiveInformationType** nello stesso Sessione di PowerShell. Nell'esempio seguente viene creata una nuova impronta digitale del documento in base al file C:\My c:\documenti\contoso Employee template. È consigliabile archiviare nuova impronta digitale come variabile in modo che è possibile utilizzare con il cmdlet **New-DlpSensitiveInformationType** nella stessa sessione di PowerShell. 
  
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

È ora possibile utilizzare il cmdlet **Get-DlpSensitiveInformationType** per trovare tutti i pacchetti di regole di classificazione dei dati DLP e in questo esempio, "Contoso Customer Confidential" fa parte dell'elenco di pacchetti regola di classificazione di dati. 
  
Infine, aggiungere il pacchetto di regole di classificazione dati "Contoso Customer Confidential" a un criterio DLP per la protezione &amp; centro conformità. In questo esempio aggiunge una regola per un criterio DLP esistente denominato "ConfidentialPolicy".

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

È inoltre possibile utilizzare il pacchetto di regole di classificazione dei dati nelle regole di trasporto in Exchange Online, come illustrato nell'esempio seguente. Per eseguire questo comando, è innanzitutto necessario [Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Si noti inoltre che richiede tempo per il pacchetto di regole di sincronizzare la sicurezza &amp; centro conformità per l'interfaccia di amministrazione di Exchange.
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

DLP rileva ora i documenti che soddisfano l'impronta digitale del documento Contoso Customer form.
  
Per informazioni di sintassi e sui parametri, vedere:

- [Nuovo DlpFingerprint](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [Nuovo DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
