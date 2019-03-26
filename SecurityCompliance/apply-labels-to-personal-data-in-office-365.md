---
title: Applicare le etichette ai dati personali in Office 365
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Informazioni su come utilizzare le etichette di Office per il piano di protezione RGPD.
ms.openlocfilehash: e31cd420fe476ace8031fc2c6e52158762814c7a
ms.sourcegitcommit: ef27da3ea5340d6e7a2eaa1288e2e005ef8e4788
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2019
ms.locfileid: "30789431"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a>Applicare le etichette ai dati personali in Office 365

 Consultare questo argomento se si usano etichette di classificazione per il piano di protezione GDPR. 

Se si usano etichette per la protezione dei dati personali in Office 365, Microsoft consiglia di iniziare con le [etichette di conservazione](labels.md). Con le etichette di conservazione è possibile:
- Usare Advanced Data Governance per applicare automaticamente le etichette in base ai tipi di informazioni sensibili o ad altri criteri.
-  Usare le etichette di conservazione con la prevenzione della perdita dei dati per applicare la protezione. 
- Usare le etichette con eDiscovery e Ricerca contenuto. 
- Usare etichette e tipi di informazioni sensibili con Cloud App Security per monitorare i dati personali che si trovano in altre app SaaS.

Le [etichette di riservatezza](sensitivity-labels.md) sono attualmente consigliate per l'applicazione di etichette a file locali e in altri provider e servizi cloud. Sono consigliate anche per file in Office 365 che richiedono la crittografia di Azure Information Protection per la protezione dei dati, ad esempio file contenenti segreti commerciali.

Al momento, l'uso di Azure Information Protection per applicare la crittografia non è consigliabile per i file in Office 365 contenenti dati soggetti al GDPR. I servizi di Office 365 attualmente non possono leggere nei file con crittografia AIP. Di conseguenza, il servizio non trova i dati sensibili in questi file.

Le etichette di riservatezza possono essere applicate ai messaggi di posta elettronica in Exchange Online e queste etichette funzionano con la prevenzione della perdita dei dati di Office 365. 

![Le etichette di Office 365 e di Azure Information Protection](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)


Nella figura:

-   Usare le etichette di conservazione per i dati personali per i file con segreti commerciali e soggetti a normative in SharePoint Online e OneDrive for Business.

-   Usare le etichette di riservatezza per i file con segreti commerciali e soggetti a normative, la posta elettronica di Exchange Online, file in altri servizi SaaS, file in datacenter locali e file in altri provider cloud.


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a>Usare le etichette di conservazione e i tipi di informazioni sensibili in Microsoft 365 per la protezione delle informazioni

La figura seguente mostra come usare le etichette di conservazione e i tipi di informazioni sensibili in criteri di etichetta, criteri di prevenzione della perdita dei dati e i criteri di Cloud App Security.

![Etichette di Office e tipi di informazioni riservate](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

Ai fini dell'accessibilità, la seguente tabella fornisce le stesse informazioni dell'illustrazione.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Elementi di classificazione</strong></th>
<th align="left"><strong>Criteri delle etichette - 2 esempi</strong></th>
<th align="left"><strong>Criteri di prevenzione della perdita dei dati - 2 esempi</strong></th>
<th align="left"><strong>I criteri di Cloud App Security per tutte le app SaaS - 1 esempio</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Etichette di conservazione. Esempi: Personale, Pubblico, Dati cliente, Dati risorse umane, Riservato, Estremamente riservato</td>
<td align="left"><p>Applicare automaticamente questa etichetta...</p>
<p>Dati cliente
</p>
<p>... ai documenti che corrispondono a questi tipi di informazioni riservate...</p>
<p>&lt;elenco dei tipi di informazioni riservate&gt;</p></td>
<td align="left"><p>Applicare la protezione...</p>
<p>&lt;definire la protezione&gt;</p>
<p>... ai documenti con questa etichetta...</p>
<p>Dati cliente
</p></td>
<td align="left"><p>Avvisa quando i file con questi attributi...</p>
<p>&lt;Attributo PII predefinito oppure espressione personalizzata&gt;</p>
<p>... in qualsiasi app SaaS approvata vengono condivisi all'esterno dell'organizzazione</p></td>
</tr>
<tr class="even">
<td align="left">Tipi di informazioni riservate. Esempi: Codice fiscale belga, numero di carta di credito, numero identità Croazia, codice fiscale Finlandese</td>
<td align="left"><p>Pubblicare le etichette per gli utenti da applicare manualmente...</p>
<p>&lt;selezionare etichette&gt;</p>
<p>... a questi percorsi...</p>
<p>&lt;tutte i percorsi oppure percorsi specifici&gt;</p></td>
<td align="left"><p>Applicare la protezione...</p>
<p>&lt;definire la protezione&gt;</p>
<p>... ai documenti che corrispondono a questi tipi di informazioni riservate&gt;</p></td>
<td align="left">Nota: gli attributi di Cloud App Security presto includeranno i tipi di informazioni riservate di Office 365 e le etichette unificate in Office 365 e Azure Information Protection.</td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a>Definire la priorità dei criteri per applicare automaticamente le etichette


Per i dati personali soggetti all'RGPD, Microsoft consiglia di applicare automaticamente le etichette utilizzando le tipologie di informazioni sensibili create per il proprio ambiente. I criteri che applicano automaticamente le etichette devono essere configurati correttamente e occorre testarli per verificare che producano i risultati previsti.


L'ordine con cui vengono creati i criteri da applicare automaticamente e il fatto che gli utenti applichino o meno queste etichette influisce sul risultato. È quindi importante pianificare attentamente l'implementazione. Ecco cosa serve sapere.

### <a name="one-label-at-a-time"></a>Un'etichetta alla volta

È possibile assegnare solo un'etichetta a un documento.

### <a name="older-auto-apply-policies-win"></a>I criteri più vecchi hanno la precedenza


Se sono presenti più regole che assegnano un'etichetta da applicare automaticamente e il contenuto soddisfa le condizioni di più regole, viene assegnata l'etichetta della regola meno recente. Per questo motivo, è importante pianificare con attenzione i criteri delle etichette prima di configurarli. Se un'organizzazione ha l'esigenza di modificare la priorità dei criteri delle etichette, è necessario eliminarli e crearli di nuovo.


### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a>Le etichette applicate manualmente dall'utente hanno la precedenza su quelle applicate automaticamente


Le etichette applicate manualmente dall'utente battono quelle applicate automaticamente. I criteri di applicazione automatica non possono sostituire un'etichetta già applicata da un utente. Gli utenti possono sostituire le etichette applicate automaticamente.

### <a name="auto-assigned-labels-can-be-updated"></a>Le etichette assegnate automaticamente possono essere aggiornate

Le etichette assegnate automaticamente possono essere aggiornate creando nuovi criteri o aggiornando quelli esistenti.


Assicurarsi che il piano di implementazione delle etichette includa:

-   Creare i criteri di applicazione automatica secondo l'ordine di priorità.


-   Allocare il tempo necessario all'applicazione automatica delle etichette prima di consentire agli utenti di applicarle manualmente. Potrebbe essere necessaria anche una settimana per applicare le etichette a tutti i contenuti che corrispondono alle condizioni.


### <a name="example-priority-for-creating-the-auto-apply-policies"></a>Esempio di priorità per creare i criteri di applicazione automatica


<table>
<thead>
<tr class="header">
<th align="left"><strong>Etichette</strong></th>
<th align="left"><strong>Ordine di priorità per creare criteri da applicare automaticamente</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Risorse umane - Dati dipendenti</td>
<td align="left">1</td>
</tr>
<tr class="even">
<td align="left">Dati cliente
</td>
<td align="left">2</td>
</tr>
<tr class="odd">
<td align="left">Estremamente riservato
</td>
<td align="left">3</td>
</tr>
<tr class="even">
<td align="left">Risorse umane - Dati sugli stipendi</td>
<td align="left">4</td>
</tr>
<tr class="odd">
<td align="left">Riservato</td>
<td align="left">5</td>
</tr>
<tr class="even">
<td align="left">Pubblico</td>
<td align="left">6</td>
</tr>
<tr class="odd">
<td align="left">Personale</td>
<td align="left">Nessun criterio di applicazione automatica</td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a>Creare le etichette e i criteri per applicare le etichette automaticamente


Creare le etichette e i criteri nel Centro sicurezza e conformità.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Passaggio</strong></th>
<th align="left"><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Assegnare autorizzazioni ai membri del team di conformità.</p></td>
<td align="left"><p>I membri del team di conformità che creeranno le etichette necessitano di autorizzazioni per utilizzare il Centro sicurezza e conformità. Andare a Autorizzazioni nel Centro sicurezza e conformità e modificare i membri del gruppo Amministratori di conformità.</p>
<p>Vedere <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Fornire agli utenti l'accesso al Centro sicurezza e conformità di Office 365</a>.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Creare etichette di conservazione.</p></td>
<td align="left">Passare a Classificazioni in Centro sicurezza e conformità, scegliere Etichette di conservazione e creare le etichette per il proprio ambiente.</td>
</tr>
<tr class="odd">
<td align="left"><p>Creare criteri di applicazione automatica per le etichette.</p></td>
<td align="left">Andare a Classificazione nel Centro sicurezza e conformità, scegliere Criteri etichette e creare i criteri di applicazione automatica delle etichette. Assicurarsi di creare questi criteri nell'ordine di priorità.</td>
</tr>
</tbody>
</table>

La figura seguente mostra come creare un'etichetta Dati cliente da applicare automaticamente.


![Creare e applicare un'etichetta per i dati del cliente](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

Nella figura:

-   Viene creata l'etichetta "Dati del cliente".

-   I tipi di informazioni riservate desiderate per l'RGPD sono: codice fiscale belga, numero di carta di credito, numero identità Croazia, codice fiscale Finlandese.

-   La creazione di un criterio di applicazione automatica assegna l'etichetta "Dati del cliente" a qualsiasi file che include uno dei tipi di informazioni riservate aggiunto al criterio.
