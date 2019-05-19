---
title: Creare una ricerca per raccogliere dati
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 360ba6a67d43a0b78b1104ae64885697009bb222
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155108"
---
# <a name="create-a-search-to-collect-data"></a>Creare una ricerca per raccogliere dati

Nella scheda **ricerche** del caso, è possibile creare una nuova ricerca facendo clic su **nuova ricerca** e seguendo la procedura guidata.

## <a name="name-your-search-and-give-description"></a>Denominare la ricerca e fornire una descrizione

Ogni ricerca con un caso deve avere un nome univoco. Facoltativamente, è possibile fornire una descrizione per la ricerca. 

## <a name="define-your-conditions"></a>Definire le proprie condizioni

È possibile definire le condizioni per la ricerca utilizzando le schede delle condizioni predefinite o utilizzando KQL (Keyword Query Language). Per ulteriori informazioni, vedere [creazione di query di ricerca](building-search-queries.md).

## <a name="choose-the-custodians-to-search-from"></a>Scegliere i depositari da cui eseguire la ricerca

Dopo aver definito le condizioni, è necessario scegliere quali posizioni si desidera ricercare. Un modo per farlo è specificare quali depositari sono già stati aggiunti al caso in cui si desidera eseguire la ricerca. Selezionando un custode, verrà eseguita la ricerca in tutte le origini dati mappate al custode. Per ulteriori informazioni su come aggiungere depositari al caso e gestire le origini dati, vedere [collaborare con i depositari](managing-custodians.md) .

## <a name="choose-non-custodial-locations"></a>Scegliere le posizioni non detentive

In alcuni casi, è possibile cercare le origini dati che non vengono mappate a un custode. In questo caso, è possibile specificare i percorsi che si desidera ricercare oppure scegliere di cercare tutti i percorsi di contenuto per uno specifico servizio di Office 365, ad esempio la ricerca in tutte le cassette postali di Exchange o in tutti i siti di SharePoint e OneDrive for business.