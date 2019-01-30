---
title: Creazione di una ricerca per raccogliere dati
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
ms.openlocfilehash: 3ebb9a40d3fb055fbb88b32175a4a22df3da44af
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607947"
---
# <a name="create-a-search-to-collect-data"></a>Creazione di una ricerca per raccogliere dati

Nella scheda **ricerche** nel caso, è possibile creare una nuova ricerca facendo clic su **New search** e seguendo la procedura guidata.

## <a name="name-your-search-and-give-description"></a>Nome della ricerca e fornire descrizione

Ogni ricerca con un caso deve avere un nome univoco. È facoltativamente possibile fornire una descrizione per la ricerca. 

## <a name="define-your-conditions"></a>Definire le condizioni

È possibile definire le condizioni per la ricerca utilizzando le schede condizione preesistente o utilizzando Keyword Query Language (KQL). Per ulteriori informazioni, vedere [creare query di ricerca](building-search-queries.md).

## <a name="choose-the-custodians-to-search-from"></a>Scegliere depositari eseguire la ricerca

Dopo aver definito le condizioni, è necessario scegliere quali percorsi da cercare. Per eseguire questa operazione è specificando quali depositari è già stato aggiunto al caso si desidera eseguire la ricerca. Selezionando un depositaria, si eseguirà la ricerca con tutte le origini dati mappate al depositaria. Per ulteriori informazioni su come aggiungere depositari al case e gestire le origini dati, vedere [Working with depositari](managing-custodians.md) .

## <a name="choose-non-custodial-locations"></a>Scegliere le posizioni non detentive

In alcuni casi, si desidera cercare nelle origini dati che non vengono mappate a un depositaria. In questo caso, è possibile specificare i percorsi che si desidera eseguire la ricerca o scegliere di cercare tutti i percorsi di contenuti per un servizio specifico di Office 365 (ad esempio ricerca SharePoint e OneDrive di tutte le cassette postali di Exchange o tutti i siti di Business).