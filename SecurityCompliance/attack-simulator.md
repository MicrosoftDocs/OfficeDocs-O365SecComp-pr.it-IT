---
title: Simulatore di attacchi in Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: In qualità di amministratore globale di Office 365, è possibile utilizzare Attack Simulator per eseguire scenari di attacco realistici nell'organizzazione. Questo può essere utile per identificare e individuare gli utenti vulnerabili prima che un attacco reale colpisca la propria azienda.
ms.openlocfilehash: ba5658dfa9075b5779f8ca09ccad3547dbddcbb5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216276"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="9f818-104">Simulatore di attacchi in Office 365</span><span class="sxs-lookup"><span data-stu-id="9f818-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="9f818-p102">**Riepilogo** Se si è un amministratore globale di Office 365 e l'organizzazione dispone di [office 365 Threat Intelligence](office-365-ti.md), è possibile utilizzare Attack Simulator per eseguire scenari di attacco realistici nell'organizzazione. Questo può essere utile per identificare e individuare gli utenti vulnerabili prima che un attacco reale impatti la linea di base. Leggere questo articolo per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="9f818-p102">**Summary** If you are an Office 365 global administrator and your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line. Read this article to learn more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f818-p103">A partire da febbraio 2019 e distribuita nei prossimi mesi, Office 365 Threat Intelligence sta diventando Office 365 Advanced Threat Protection Plan 2, con ulteriori funzionalità di protezione dalle minacce. Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="9f818-p103">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="9f818-110">Gli attacchi</span><span class="sxs-lookup"><span data-stu-id="9f818-110">The Attacks</span></span>

<span data-ttu-id="9f818-111">Sono attualmente disponibili tre tipi di simulazioni di attacco:</span><span class="sxs-lookup"><span data-stu-id="9f818-111">Three kinds of attack simulations are currently available:</span></span>
  
- [<span data-ttu-id="9f818-112">Nome visualizzato Spear-attacco di phishing</span><span class="sxs-lookup"><span data-stu-id="9f818-112">Display name spear-phishing attack</span></span>](attack-simulator.md#spearphish)
    
- [<span data-ttu-id="9f818-113">Attacco spray per la password</span><span class="sxs-lookup"><span data-stu-id="9f818-113">Password-spray attack</span></span>](attack-simulator.md#passwordspray)
    
- [<span data-ttu-id="9f818-114">Attacco per la password con forza bruta</span><span class="sxs-lookup"><span data-stu-id="9f818-114">Brute-force password attack</span></span>](attack-simulator.md#bruteforce)
    
<span data-ttu-id="9f818-p104">Per l'avvio di un attacco, è possibile utilizzare l'autenticazione a più fattori nell'account che si sta utilizzando per eseguire attacchi simulati. Inoltre, è necessario essere un amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9f818-p104">For an attack to be successfully launched, you use multi-factor authentication on the account you are using to run simulated attacks. In addition, you must be an Office 365 global administrator.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9f818-117">Il supporto per l'accesso condizionale è disponibile a breve.</span><span class="sxs-lookup"><span data-stu-id="9f818-117">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="9f818-118">Per accedere a simulatore di attacco, &amp; nel centro sicurezza e conformità scegliere **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="9f818-118">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="9f818-119">Prima di iniziare...</span><span class="sxs-lookup"><span data-stu-id="9f818-119">Before you begin...</span></span>

<span data-ttu-id="9f818-120">Assicurarsi che l'utente e l'organizzazione soddisfino i seguenti requisiti per il simulatore di attacco:</span><span class="sxs-lookup"><span data-stu-id="9f818-120">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
      
- <span data-ttu-id="9f818-p105">La posta elettronica dell'organizzazione è ospitata in Exchange Online. (Attack Simulator non è disponibile per i server di posta elettronica locali.)</span><span class="sxs-lookup"><span data-stu-id="9f818-p105">Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="9f818-123">Si è un amministratore globale di Office 365</span><span class="sxs-lookup"><span data-stu-id="9f818-123">You are an Office 365 global administrator</span></span>
    
- <span data-ttu-id="9f818-124">L'organizzazione utilizza [l'autenticazione a più fattori per gli utenti di Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="9f818-124">Your organization is using [Multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)</span></span>
 
- <span data-ttu-id="9f818-125">l'organizzazione dispone [di Office 365 threat Intelligence](office-365-ti.md), con simulatore di attacco visibile &amp; nel centro sicurezza e conformità (andare a **Threat management** \> **Attack simulator**)</span><span class="sxs-lookup"><span data-stu-id="9f818-125">Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span><br/><span data-ttu-id="9f818-126">![Threat Management-simulatore d'attacco](media/ThreatMgmt-AttackSimulator.png)</span><span class="sxs-lookup"><span data-stu-id="9f818-126">![Threat management - Attack Simulator](media/ThreatMgmt-AttackSimulator.png)</span></span>

    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="9f818-127">Nome visualizzato Spear-attacco di phishing</span><span class="sxs-lookup"><span data-stu-id="9f818-127">Display name spear-phishing attack</span></span>

<span data-ttu-id="9f818-p106">Il phishing è un termine generico per una vasta serie di attacchi classificati come un attacco stile di social engineering. Questo attacco è concentrato sul phishing Spear, un attacco più mirato che si rivolge a un gruppo specifico di persone o di un'organizzazione. In genere, un attacco personalizzato con alcuni ricognizione eseguito e utilizzando un nome visualizzato che genererà la fiducia nel destinatario, ad esempio un messaggio di posta elettronica che sembra provenire da un dirigente all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9f818-p106">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="9f818-p107">Questo attacco è incentrato sull'eventualità di modificare il messaggio a cui sembra abbia avuto origine cambiando il nome visualizzato e l'indirizzo di origine. Quando gli attacchi Spear-phishing hanno esito positivo, i criminali informatici accedono alle credenziali degli utenti.</span><span class="sxs-lookup"><span data-stu-id="9f818-p107">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="9f818-133">Per simulare un attacco di Spear-phishing</span><span class="sxs-lookup"><span data-stu-id="9f818-133">To simulate a spear-phishing attack</span></span>

![Comporre il corpo della posta elettronica](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="9f818-135">È possibile creare l'editor HTML RTF direttamente nel campo **corpo del messaggio di posta elettronica** o collaborare con l'origine HTML.</span><span class="sxs-lookup"><span data-stu-id="9f818-135">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>
  
1. <span data-ttu-id="9f818-136">Nel [Centro sicurezza &amp; e conformità](https://protection.office.com)scegliere **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="9f818-136">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="9f818-137">Specificare un nome di campagna significativo per l'attacco o selezionare un modello.</span><span class="sxs-lookup"><span data-stu-id="9f818-137">Specify a meaningful campaign name for the attack or select a template.</span></span> <br/>![Pagina iniziale di phishing](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="9f818-p108">Specificare i destinatari di destinazione. Può trattarsi di singoli o gruppi nell'organizzazione. Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange online in modo che l'attacco abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9f818-p108">Specify the target recipients. This can be individuals or groups in your organization. Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span> <br/>![Selezione destinatario](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="9f818-143">Configurare i dettagli di posta elettronica di phishing.</span><span class="sxs-lookup"><span data-stu-id="9f818-143">Configure the Phishing email details.</span></span> <br/>![Configurare i dettagli della posta elettronica](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/><span data-ttu-id="9f818-p109">La formattazione HTML può essere complessa o di base come necessario per la campagna. Poiché il formato del messaggio di posta elettronica è HTML, è possibile inserire immagini e testo per migliorare la credibilità. È possibile controllare l'aspetto del messaggio ricevuto nel client di posta elettronica di ricezione.</span><span class="sxs-lookup"><span data-stu-id="9f818-p109">The HTML formatting can be as complex or basic as your campaign needs. As the email format is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.</span></span>
    
5. <span data-ttu-id="9f818-p110">Specificare il testo per il campo **from (Name)** . Si tratta del campo che viene visualizzato nel **nome visualizzato** nel client di posta elettronica di ricezione.</span><span class="sxs-lookup"><span data-stu-id="9f818-p110">Specify text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
6. <span data-ttu-id="9f818-p111">Specificare il testo o il campo **da** . Si tratta del campo che viene visualizzato come indirizzo di posta elettronica del mittente nel client di posta elettronica di ricezione.</span><span class="sxs-lookup"><span data-stu-id="9f818-p111">Specify text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client. </span></span><br/><span data-ttu-id="9f818-p112">È possibile immettere uno spazio dei nomi di posta elettronica esistente all'interno dell'organizzazione (in questo modo l'indirizzo di posta elettronica viene effettivamente risolto nel client di ricezione, facilitando un modello di attendibilità molto elevato) oppure è possibile immettere un indirizzo di posta elettronica esterno. L'indirizzo di posta elettronica specificato non deve esistere effettivamente, ma ha bisogno di seguire il formato di un indirizzo SMTP valido, ad esempio User @ NomeDominio. Extension.</span><span class="sxs-lookup"><span data-stu-id="9f818-p112">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
7. <span data-ttu-id="9f818-p113">Usando il selettore a discesa, selezionare un URL del server di accesso di phishing che rispecchi il tipo di contenuto che si avrà all'interno dell'attacco. È possibile scegliere tra diversi URL a tema, ad esempio recapito dei documenti, tecnico, retribuzione e così via. Questo è effettivamente l'URL a cui gli utenti designati devono fare clic.</span><span class="sxs-lookup"><span data-stu-id="9f818-p113">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
8. <span data-ttu-id="9f818-p114">Specificare un URL della pagina di destinazione personalizzata. In questo modo gli utenti verranno reindirizzati a un URL specificato al termine di un attacco con esito positivo. Se si dispone di un training di sensibilizzazione interno, ad esempio, è possibile specificarlo qui.</span><span class="sxs-lookup"><span data-stu-id="9f818-p114">Specify a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.</span></span>
    
9. <span data-ttu-id="9f818-p115">Specificare il testo per il campo **Subject** . Si tratta del campo che viene visualizzato come **nome del soggetto** nel client di posta elettronica di ricezione.</span><span class="sxs-lookup"><span data-stu-id="9f818-p115">Specify text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
10. <span data-ttu-id="9f818-161">Comporre il **corpo del messaggio di posta elettronica** che riceverà il destinatario.</span><span class="sxs-lookup"><span data-stu-id="9f818-161">Compose the **Email body** that the target will receive.</span></span> <br/><span data-ttu-id="9f818-162">`${username}`inserisce il nome della destinazione nel corpo della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9f818-162">`${username}` inserts the targets name into the Email body.</span></span> <br/><span data-ttu-id="9f818-163">`${loginserverurl}`inserisce l'URL in cui si desidera che gli utenti di destinazione clicchino</span><span class="sxs-lookup"><span data-stu-id="9f818-163">`${loginserverurl}` inserts the URL we want target users to click</span></span> 
    
11. <span data-ttu-id="9f818-p116">Fare clic su **Avanti,** quindi su **fine** per avviare l'attacco. Il messaggio di posta elettronica di phishing Spear viene recapitato alle cassette postali dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="9f818-p116">Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="9f818-166">Attacco spray per la password</span><span class="sxs-lookup"><span data-stu-id="9f818-166">Password-spray attack</span></span>

<span data-ttu-id="9f818-p117">Un attacco di spruzzatura della password in un'organizzazione viene in genere utilizzato dopo che un attore cattivo ha acquisito un elenco di utenti validi dal tenant. L'attore cattivo conosce le password comuni utilizzate dalle persone. Si tratta di un attacco ampiamente utilizzato, poiché si tratta di un attacco a basso costo da eseguire e più difficile da rilevare rispetto alla forza bruta.</span><span class="sxs-lookup"><span data-stu-id="9f818-p117">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant. The bad actor knows about common passwords that people use. This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="9f818-170">Questo attacco consente di specificare una password comune rispetto a una base di utenti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="9f818-170">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="9f818-171">Per simulare un attacco spray per la password</span><span class="sxs-lookup"><span data-stu-id="9f818-171">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="9f818-172">Nel [Centro sicurezza &amp; e conformità](https://protection.office.com)scegliere **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="9f818-172">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="9f818-173">Specificare il nome di una campagna significativa per l'attacco.</span><span class="sxs-lookup"><span data-stu-id="9f818-173">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="9f818-p118">Specificare i destinatari di destinazione. Può trattarsi di singoli o gruppi nell'organizzazione. Un destinatario di destinazione deve disporre di una cassetta postale di Exchange online in modo che l'attacco abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9f818-p118">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="9f818-p119">Specificare una password da utilizzare per l'attacco. Ad esempio, una password comune e pertinente che è possibile `Fall2017`provare è. Un altro potrebbe `Spring2018`essere, `Password1`o.</span><span class="sxs-lookup"><span data-stu-id="9f818-p119">Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="9f818-180">Scegliere **fine** per avviare l'attacco.</span><span class="sxs-lookup"><span data-stu-id="9f818-180">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="9f818-181">Attacco per la password con forza bruta</span><span class="sxs-lookup"><span data-stu-id="9f818-181">Brute-force password attack</span></span>

<span data-ttu-id="9f818-p120">Un attacco di password con forza bruta nei confronti di un'organizzazione viene in genere utilizzato dopo che un attore non valido ha acquisito un elenco di utenti chiave dal tenant. Questo attacco si concentra sul tentativo di un set di password su un singolo account utente.</span><span class="sxs-lookup"><span data-stu-id="9f818-p120">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant. This attack focuses on trying a set of passwords on a single user's account.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="9f818-184">Per simulare un attacco di password con forza bruta</span><span class="sxs-lookup"><span data-stu-id="9f818-184">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="9f818-185">Nel [Centro sicurezza &amp; e conformità](https://protection.office.com)scegliere **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="9f818-185">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="9f818-186">Specificare il nome di una campagna significativa per l'attacco.</span><span class="sxs-lookup"><span data-stu-id="9f818-186">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="9f818-p121">Specificare il destinatario di destinazione. Un destinatario di destinazione deve disporre di una cassetta postale di Exchange online in modo che l'attacco abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9f818-p121">Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="9f818-p122">Specificare un set di password da utilizzare per l'attacco. A tale scopo, è possibile utilizzare un file di testo (con estensione txt) per l'elenco delle password. Il file di testo non può superare i 10 MB nelle dimensioni dei file. Utilizzare una password per riga e assicurarsi di includere un ritorno a capo dopo l'ultima password dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="9f818-p122">Specify a set of passwords to use for the attack. To do this, you can use a text (.txt) file for your list of passwords. The text file cannot exceed 10 MB in file size. Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>
    
5. <span data-ttu-id="9f818-193">Scegliere **fine** per avviare l'attacco.</span><span class="sxs-lookup"><span data-stu-id="9f818-193">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="9f818-194">Nuove funzionalità in Attack Simulator</span><span class="sxs-lookup"><span data-stu-id="9f818-194">New features in Attack Simulator</span></span>

<span data-ttu-id="9f818-p123">Sono state aggiunte nuove funzionalità al simulatore di attacco. Sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f818-p123">New features are being added to Attack Simulator. These include:</span></span>
- <span data-ttu-id="9f818-p124">**Funzionalità di creazione di report avanzate**. È possibile visualizzare i dati, ad esempio il tempo più rapido (o più lento) per aprire un messaggio di posta elettronica di simulazione di attacco, ovvero il tempo più rapido (o più lento) per fare clic su un collegamento nel messaggio e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="9f818-p124">**Advanced reporting capabilities**. You'll be able to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more.</span></span>
- <span data-ttu-id="9f818-p125">**Editor modelli di posta elettronica**. È possibile creare un modello di posta elettronica personalizzato e riutilizzabile che è possibile utilizzare per simulazioni di attacco future.</span><span class="sxs-lookup"><span data-stu-id="9f818-p125">**Email template editor**. You can create a custom, reusable email template that you can use for future attack simulations.</span></span>

<span data-ttu-id="9f818-201">Visitare la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) per vedere cosa c'è in sviluppo, cosa è in uscita e cosa è già stato avviato.</span><span class="sxs-lookup"><span data-stu-id="9f818-201">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>



