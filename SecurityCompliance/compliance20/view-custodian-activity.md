---
title: Visualizza depositaria controllo attività
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8219ae8a061f6d08dd37da5b7f2974dd86c68f04
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607888"
---
# <a name="viewing-custodian-audit-activity"></a>Visualizzazione depositaria controllare l'attività

Sai dove trovare se un utente di visualizzata un documento specifico o eliminato un elemento dalla cassetta postale? EDiscovery avanzate (Preview) è ora integrato con lo strumento di controllo Registro ricerca esistente in & la sicurezza centro conformità. Tramite questa esperienza incorporata, è possibile utilizzare lo strumento di gestione depositaria eDiscovery avanzate (Preview) allo scopo di facilitare le indagini facilmente accedendo e cercare l'attività depositari all'interno del case.

## <a name="before-you-begin"></a>Informazioni preliminari

È necessario disporre del ruolo registri di controllo View-Only o i registri di controllo di Exchange Online per la ricerca nel Registro di controllo di Office 365. Per impostazione predefinita, questi ruoli vengono assegnati per la gestione della conformità e i gruppi di ruoli Gestione organizzazione nella pagina autorizzazioni nell'interfaccia di amministrazione di Exchange. Per assegnare a un utente la possibilità di eseguire ricerche nel Registro di controllo eDiscovery avanzate (Preview) con il livello minimo di privilegi, si può creare un gruppo di ruoli personalizzati in Exchange Online, aggiungere il ruolo registri di controllo View-Only o i registri di controllo e quindi aggiungere l'utente come membri del nuovo gr di ruolo Includi gruppo. Per ulteriori informazioni, vedere Manage role groups in Exchange Online.

> [!IMPORTANT]
> Se si assegna un utente il ruolo registri di controllo View-Only o i registri di controllo nella pagina autorizzazioni di sicurezza & centro conformità, non saranno in grado di eseguire ricerche nel Registro di controllo di Office 365. È necessario assegnare le autorizzazioni in Exchange Online. Ciò avviene perché il cmdlet sottostante utilizzato per cercare il Registro di controllo è un cmdlet di Exchange Online.

## <a name="step-1-create-an-advanced-ediscovery-preview-audit-log-search"></a>Passaggio 1: Creare una ricerca di log di controllo eDiscovery avanzate (Preview)

   1. Selezionare un caso esistente **sicurezza & centro conformità gt _ avanzate eDiscovery (Preview)**.
   
   2. Passare alla scheda **depositari** e selezionare un depositaria.
   
   3. Dopo aver selezionato un depositaria, fare clic su **Visualizza depositaria attività** dal riquadro dettagli.
   
   4. Configurare i criteri di ricerca seguenti:
      
      r. **delle attività** - scegliere l'elenco a discesa per visualizzare le attività che è possibile cercare. Dopo aver eseguito la ricerca, vengono visualizzati solo i record di verifica per le attività selezionate. Selezionare **Mostra i risultati per tutte le attività** visualizzerà i risultati per tutte le attività che soddisfano i criteri di ricerca.
      
      **Data di inizio e Data fine** - b. selezionare un intervallo di data e ora per visualizzare gli eventi che si sono verificati durante questo periodo. Ultimi sette giorni sono selezionati per impostazione predefinita. Data e ora sono disponibili in formato ora UTC (Coordinated Universal Time). L'intervallo di date massimo che è possibile specificare sia un anno.
      
      c. **depositari** - fare clic su in questa casella e quindi selezionare un depositaria specifico per visualizzare Criteri di ricerca di risultati per. Nell'elenco dei risultati vengono visualizzati i record di controllo per l'attività selezionata eseguite dagli utenti che selezionare questa casella.
    
    1. Fare clic su **ricerca** per eseguire la ricerca utilizzando i criteri di ricerca. I risultati della ricerca sono stati caricati e dopo pochi secondi vengono visualizzati nell'area risultati della pagina di ricerca depositaria attività. 

## <a name="step-2-view-the-audit-log-search-results"></a>Passaggio 2: Visualizzare i risultati di ricerca di log di controllo

I risultati di una ricerca dei registri di controllo vengono visualizzati nella casella risultati nella pagina Registro di controllo depositaria. Un massimo di 5.000 eventi (più recenti) vengono visualizzati in incrementi di 150 eventi. Per visualizzare più eventi è possibile utilizzare la barra di scorrimento nel riquadro dei risultati oppure è possibile premere MAIUSC + freccia giù per visualizzare gli eventi successivamente 150.

I risultati includono le seguenti informazioni relative a ogni evento restituito dalla ricerca.
- **Data**: data e ora (in formato UTC) quando si è verificato l'evento.

- **Indirizzo IP**: l'indirizzo IP del dispositivo utilizzato quando ha effettuato l'accesso all'attività. L'indirizzo IP viene visualizzato in formato di indirizzo di un indirizzo IPv4 o IPv6.

- **Utente**: l'utente (o account di servizio) che ha eseguito l'azione che ha attivato l'evento.

- **Attività**: attività eseguite dall'utente. Questo valore corrisponde all'attività selezionata nell'elenco a discesa delle attività. Per un evento dal Registro di controllo di amministrazione di Exchange, il valore di questa colonna è un cmdlet di Exchange.

- **Articolo**: l'oggetto che è stato creato o modificato a causa di attività corrispondente. Ad esempio, il file che è stato visualizzato o modificato o l'account utente che è stato aggiornato. Non tutte le attività con un valore in questo articolo.

- **Dettagli**: ulteriori dettagli su un'attività. Non tutte le attività, saranno necessario un valore.

## <a name="step-3-filter-the-search-results"></a>Passaggio 3: Filtrare i risultati della ricerca

Oltre a ordinare, è inoltre possibile filtrare i risultati di una ricerca dei registri di controllo. Ciò consente di filtrare rapidamente i risultati per un utente specifico o l'attività. 

Per filtrare i risultati:

 1. Creare ed eseguire una ricerca dei registri di controllo.
  
2. Quando vengono visualizzati i risultati, fare clic su **filtrare i risultati**.
 
3. Le caselle parola chiave vengono visualizzate in ogni intestazione di colonna.
  
4. Fare clic su una delle caselle in un'intestazione di colonna e digitare una parola o frase, a seconda della colonna che si desidera filtrare in. I risultati verranno dinamicamente modificare nuovamente per visualizzare gli eventi che soddisfano il filtro.
  
5. Per cancellare un filtro, fare clic su **X** nella casella filtro oppure fare clic su **Nascondi filtro**.

## <a name="export-the-search-results-to-a-file"></a>Esportare i risultati della ricerca in un file

È possibile esportare i risultati di una ricerca dei registri di controllo in un file di virgole (CSV) nel computer locale. È possibile aprire il file di Microsoft Excel e utilizzare caratteristiche, ad esempio ricerca, ordinamento, filtro e la divisione di una singola colonna (che contiene le celle multivalore) in più colonne.

1. Eseguire una ricerca dei registri di controllo e quindi modificare i criteri di ricerca fino a ottenere i risultati desiderati.
  
2. Fare clic su Esporta risultati e selezionare una delle opzioni seguenti:

    - **Salva caricato i risultati:** Selezionare questa opzione per esportare solo le voci visualizzate nella casella **risultati** della pagina di **ricerca dei registri di controllo depositaria** . Il file CSV che può essere scaricato contiene le stesse colonne (e dati) visualizzato nella pagina (data, utente, attività, elemento e i dettagli). Una colonna aggiuntiva (intitolata **ulteriori**) è incluso nel file CSV contenente informazioni dalla voce di registro di controllo. Dal momento che vengono esportati gli stessi risultati caricato (e visualizzabili) nella pagina di ricerca del Registro di controllo, un massimo di 5.000 voci vengono esportati.
        
    - **Scarica tutti i risultati:** Selezionare questa opzione per esportare tutte le voci dal Registro di controllo di Office 365 che soddisfano i criteri di ricerca. Per un elevato numero di risultati della ricerca, selezionare questa opzione per scaricare tutte le voci dal Registro di controllo oltre a 5.000 risultati che possono essere visualizzati nella pagina di ricerca **depositaria Audit log** . Questa opzione scaricherà i dati non elaborati dal Registro di controllo in un file CSV e contiene informazioni aggiuntive dalla voce del Registro di controllo in una colonna denominata AuditData. Può richiedere più tempo per scaricare il file se si sceglie questa opzione di esportazione in quanto il file può essere molto più grande di quella che può essere scaricato se si sceglie l'opzione altro.
    
      > [!IMPORTANT]
      > È possibile scaricare un massimo di 50.000 voci in un file CSV da una ricerca dei registri di controllo singolo. Se 50.000 voci vengono scaricate nel file CSV, è probabile che può assumere sono presenti più di 50.000 eventi che soddisfano i criteri di ricerca. Per esportare più di questo limite, provare a utilizzare un intervallo di date per ridurre il numero di voci del Registro di controllo. Potrebbe essere necessario eseguire più ricerche con dimensioni inferiori intervalli di date per esportare le voci più di 50.000.
        

3. Dopo aver selezionato un'opzione di esportazione, nella parte inferiore della finestra in cui viene chiesto di aprire il file CSV, salvarlo nella cartella download o salvarlo in una determinata cartella viene visualizzato un messaggio

[!NOTE] 
 Per ulteriori informazioni sulla visualizzazione, il filtro o l'esportazione dei risultati di ricerca di log di controllo, vedere:
   - Visualizza l'elenco di attività controllata 
   - Prima di iniziare: I registri di controllo unificato
 