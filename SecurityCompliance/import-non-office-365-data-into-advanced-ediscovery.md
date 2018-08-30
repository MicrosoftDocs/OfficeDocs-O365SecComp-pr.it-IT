---
title: Importare i contenuti non Office 365 per l'analisi di Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 5/25/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Come blob in modo che può essere analizzata con AeD alla procedura seguente per importare il contenuto che non vengono archiviato in Office 365 un Azure
ms.openlocfilehash: ab6c7ac76a159603a34719aa8edb51de3a4fabbb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531464"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a>Importare i contenuti non Office 365 per l'analisi di Advanced eDiscovery

Non tutti i documenti che potrebbe essere necessario per l'analisi con Office 365 avanzate eDiscovery risiederanno in Office 365. Con il contenuto Non Office 365 importare funzionalità di eDiscovery avanzate che è possibile caricare documenti che non live in Office 365 (ad eccezione dei file PST) in un oggetto blob storage maiuscole collegati e Azure e analizzarli con eDiscovery avanzate. Questa procedura viene illustrato come portare i documenti non Office 365 in eDiscovery avanzate per l'analisi.
  
> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
> [!NOTE]
> È possibile acquistare una sottoscrizione di componente aggiuntivo di Office 365 avanzate eDiscovery dati spazio di archiviazione per il contenuto non Office 365. Ciò è disponibile solo per il contenuto da analizzare con eDiscovery avanzate. Seguire i passaggi descritti in [acquisto o edit e componenti aggiuntivi per Office 365 per aziende](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) e il componente aggiuntivo di Office 365 avanzate archiviazione eDiscovery di acquisto. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

Utilizzando la caratteristica di caricamento Non Office 365, come descritto in questa procedura è necessario disporre:
  
- Un Office 365 E3 con sottoscrizione E5 o componente aggiuntivo di conformità avanzate
    
- Tutti i depositari viene caricato il cui contenuto non Office 365 devono disporre E3 con licenze E5 o componente aggiuntivo di conformità avanzate
    
- Un caso eDiscovery esistente
    
- Tutti i file per caricamento raccolte in cartelle in cui vi è una cartella per depositaria e le cartelle è denominato in questo formato *alias@domainname* . *Alias@domainname* deve essere dominio e l'alias di utenti di Office 365. È possibile raccogliere tutte le cartelle *alias@domainname* in una cartella radice. La cartella radice può contenere solo le cartelle *alias@domainname* , non deve esistere alcun file separati nella cartella radice 
    
- Un account che è un eDiscovery Manager o un amministratore di eDiscovery
    
- [Microsoft Azure archiviazione strumenti](https://aka.ms/downloadazcopy) installati in un computer che dispone dell'accesso alla struttura di cartelle del contenuto non Office 365. 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Caricare il contenuto non Office 365 in eDiscovery avanzate

1. Come eDiscovery Manager o eDiscovery amministratore, aprire **eDiscovery**e aprire quello che verranno caricati i dati non Office 365 in. Se è necessario creare un caso, vedere [gestione dei casi di eDiscovery in Office 365 Security &amp; centro conformità](manage-ediscovery-cases.md)
    
2. Fare clic su **passa a eDiscovery avanzate**
    
3. In **tipo di origine** selezionare **dati Non Office 365**.
    
4. Fare clic su **Aggiungi contenitore**. Nome del contenitore e aggiungere una descrizione.
    
5. Selezionare il contenitore appena aggiunto dall'elenco del contenitore e copiare l'URL che verrà visualizzato nel riquadro dei dettagli contenitore e quindi chiusura il riquadro
    
6. Aprire un prompt dei comandi come amministratore e passare alla cartella in cui si dispone AzCopy installato...
    
7. Creare la riga di comando AzCopy per caricare i file simile alla seguente:
    
    /Origine AzCopy: " *percorso completo della cartella radice sul computer locale* " /Dest: " *URL contenitore fino a ma non è incluso il?* " /DestSAS: " *resto dell'url contenitore dal? alla fine* "/ S. 
    
    Ad esempio, utilizzo di questi valori: 
    
  - cartella radice - C:\Collected dati 
    
  - url contenitore - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp; sr = c&amp;si = NonOfficeData15 %7 C 0&amp;sig = % Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA 3D
    
    la sintassi della riga di comando AzCopy è:
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    Per ulteriori informazioni su Azcopy sintassi, vedere [il trasferimento dei dati con AzCopy su Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) . 
    
    > [!IMPORTANT]
    > Deve essere presente una cartella principale per utente e il nome della cartella deve essere nel formato *alias@domainname* . 
  
8. Dopo aver completato le cartelle del caricamento, tornare a eDiscovery avanzate. Il contenuto delle cartelle che è stata caricata è ora pronto per l'elaborazione di eDiscovery avanzate. Selezionare il contenitore e fare clic sul pulsante di processo. Per ulteriori informazioni su eDiscovery avanzate vedere elaborazione, [eseguita la funzionalità di processo e caricamento dei dati in Office 365 avanzate eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
    
    > [!IMPORTANT]
    > Dopo il contenitore viene elaborato correttamente di eDiscovery avanzate, non sarà in grado di aggiungere nuovo contenuto per l'archiviazione SAS in Azure. Se si raccolta contenuto aggiuntivo e si desidera aggiungere al caso di analisi avanzate eDiscovery, è necessario creare un nuovo contenitore di **dati Non Office 365** e ripetere questa procedura. 
  
    > [!NOTE]
    > Se il contenitore *non elabora correttamente a causa di problemi dei nomi di cartella* e quindi risolvere i problemi, è comunque necessario creare un nuovo contenitore e la riconnessione e caricare nuovamente utilizzando le procedure descritte in questo articolo. 
  

