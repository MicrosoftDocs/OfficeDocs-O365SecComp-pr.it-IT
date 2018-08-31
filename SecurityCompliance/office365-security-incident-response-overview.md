---
title: Intervento in caso di incidente di sicurezza di Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: Questa soluzione fornisce le informazioni potrebbero avere gli attacchi si quali i più comune cyber correlati alla sicurezza in Office 365 e come rispondere a tali
ms.openlocfilehash: 3b72b9bf8c68df2fcc1233b56ee33eaf45695bfe
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531216"
---
# <a name="office-365-security-incident-response"></a><span data-ttu-id="6f318-103">Intervento in caso di incidente di sicurezza di Office 365</span><span class="sxs-lookup"><span data-stu-id="6f318-103">Office 365 Security Incident Response</span></span>

 <span data-ttu-id="6f318-104">**Riepilogo:** Questa soluzione fornisce le informazioni che cosa sono gli indicatori di attacchi cyber protezione più comuni in Office 365, come positivamente verificare un attacco di tipo specificato e come rispondere a esso.</span><span class="sxs-lookup"><span data-stu-id="6f318-104">**Summary:** This solution tells you what the indicators are for the most common cyber-security attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>
  
## <a name="overview"></a><span data-ttu-id="6f318-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="6f318-105">Overview</span></span>
<span data-ttu-id="6f318-p101">Non tutti gli attacchi cyber possono essere identità. Chi effettua l'attacco è costantemente alla ricerca per la nuovi punti deboli nella strategia di difesa o sono sfrutta precedenti. La procedura di riconoscono un attacco consente di rispondere più rapidamente a esso, che si riduce la durata dei problemi di protezione.</span><span class="sxs-lookup"><span data-stu-id="6f318-p101">Not all cyber attacks can be thwarted. Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones. Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="6f318-p102">In questa serie di articolo vengono fornite informazioni che un tipo particolare di attacco potrebbe aspetto in Office 365 e permette di utilizzare i passaggi da eseguire per rispondere. Punti di ingresso rapido a informazioni sono:</span><span class="sxs-lookup"><span data-stu-id="6f318-p102">This series of article helps you understand what a particular type of attack might look like in Office 365 and gives you steps you can take to respond. They are quick entry points to understanding:</span></span>
 
- <span data-ttu-id="6f318-111">Quali l'attacco e del relativo funzionamento.</span><span class="sxs-lookup"><span data-stu-id="6f318-111">What the attack is and how it works.</span></span>
- <span data-ttu-id="6f318-112">Che cosa si disconnette, viene chiamato gli indicatori di compromesso (IOC), cercare e come ricercati.</span><span class="sxs-lookup"><span data-stu-id="6f318-112">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>
- <span data-ttu-id="6f318-113">Come verificare positivamente l'attacco.</span><span class="sxs-lookup"><span data-stu-id="6f318-113">How to positively confirm the attack.</span></span>
- <span data-ttu-id="6f318-114">Operazioni da eseguire per esclusi l'attacco e migliori proteggere l'organizzazione in futuro.</span><span class="sxs-lookup"><span data-stu-id="6f318-114">Steps to take to cut off the attack and better protect your organization in the future.</span></span>
- <span data-ttu-id="6f318-115">Collegamenti a informazioni dettagliate su ciascuna attaccano di tipo.</span><span class="sxs-lookup"><span data-stu-id="6f318-115">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="6f318-116">Seleziona qui mensile altri articoli verranno aggiunti nel tempo.</span><span class="sxs-lookup"><span data-stu-id="6f318-116">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="6f318-117">Rilevare e correggere articoli</span><span class="sxs-lookup"><span data-stu-id="6f318-117">Detect and Remediate Articles</span></span>
- [<span data-ttu-id="6f318-118">Rilevare e rimediare a concessioni di consenso illecite in Office 365</span><span class="sxs-lookup"><span data-stu-id="6f318-118">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)
- [<span data-ttu-id="6f318-119">Rilevare e correggere le regole di Outlook e injections nei moduli personalizzati in Office 365</span><span class="sxs-lookup"><span data-stu-id="6f318-119">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)
 
## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="6f318-120">Protezione di Office 365 come alla sicurezza informatica pro</span><span class="sxs-lookup"><span data-stu-id="6f318-120">Secure Office 365 like a cybersecurity pro</span></span>
<span data-ttu-id="6f318-p103">La sottoscrizione a Office 365 è dotato di un insieme completo di funzionalità di protezione che è possibile utilizzare per proteggere i dati e gli utenti.  Utilizzare il [roadmap di protezione di Office 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) per l'implementazione Microsoft di procedure consigliate per la protezione di Office 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="6f318-p103">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.  Use the [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>
- <span data-ttu-id="6f318-p104">Attività per raggiungere i primi 30 giorni.  Questi hanno effetto immediato e sono basso impatto per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6f318-p104">Tasks to accomplish in the first 30 days.  These have immediate affect and are low-impact to your users.</span></span>
- <span data-ttu-id="6f318-p105">Attività da eseguire per 90 giorni. Queste un po' di tempo maggiore pianificare e implementare ma migliorare notevolmente le condizioni di sicurezza generali</span><span class="sxs-lookup"><span data-stu-id="6f318-p105">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture</span></span>
- <span data-ttu-id="6f318-p106">Oltre a 90 giorni. Questi miglioramenti build per il lavoro di 90 giorni primo.</span><span class="sxs-lookup"><span data-stu-id="6f318-p106">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>






