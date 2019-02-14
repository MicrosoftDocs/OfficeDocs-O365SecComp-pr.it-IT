---
title: Simulatore di attacchi in Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: Amministratore globale di Office 365, è possibile utilizzare simulatore di attacco per l'esecuzione di scenari di attacco realistico all'interno dell'organizzazione. Ciò consente di identificare e trovare gli utenti vulnerabili prima di un attacco reale accede a un'azienda.
ms.openlocfilehash: 77de6af6546ae584e3bd25c0d1a59d9f26928f33
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995167"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="2b152-104">Simulatore di attacchi in Office 365</span><span class="sxs-lookup"><span data-stu-id="2b152-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="2b152-p102">**Riepilogo** Se si è un amministratore globale di Office 365 e l'organizzazione dispone di [Business Intelligence di rischio di Office 365](office-365-ti.md), è possibile utilizzare simulatore di attacco per l'esecuzione di scenari di attacco realistico all'interno dell'organizzazione. Ciò consente di identificare e individuare gli utenti vulnerabili prima di un attacco reale un impatto significativo sulla parte inferiore. In questo articolo per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="2b152-p102">**Summary** If you are an Office 365 global administrator and your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line. Read this article to learn more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b152-p103">A partire da febbraio 2019 e distribuzione sui prossimi mesi, Business Intelligence di Office 365 rischio sta diventando Office 365 avanzate Threat Protection piano 2, le funzionalità di protezione aggiuntive rischio. Per ulteriori informazioni, vedere [i piani Office 365 avanzate Threat Protection e i prezzi](https://products.office.com/exchange/advance-threat-protection) e [Office 365 avanzate Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="2b152-p103">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="2b152-110">Gli attacchi</span><span class="sxs-lookup"><span data-stu-id="2b152-110">The Attacks</span></span>

<span data-ttu-id="2b152-111">Tre tipi di simulazioni attacco sono attualmente disponibili:</span><span class="sxs-lookup"><span data-stu-id="2b152-111">Three kinds of attack simulations are currently available:</span></span>
  
- [<span data-ttu-id="2b152-112">Attacco spear phishing nome di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="2b152-112">Display name spear-phishing attack</span></span>](attack-simulator.md#spearphish)
    
- [<span data-ttu-id="2b152-113">Attacco di tipo spray password</span><span class="sxs-lookup"><span data-stu-id="2b152-113">Password-spray attack</span></span>](attack-simulator.md#passwordspray)
    
- [<span data-ttu-id="2b152-114">Attacchi di forza bruta attacco password</span><span class="sxs-lookup"><span data-stu-id="2b152-114">Brute-force password attack</span></span>](attack-simulator.md#bruteforce)
    
<span data-ttu-id="2b152-p104">Per un attacco in cui deve essere avviato correttamente, si utilizza l'autenticazione a più fattori l'account utilizzato per eseguire gli attacchi di tipo simulati. Inoltre, è necessario essere un amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2b152-p104">For an attack to be successfully launched, you use multi-factor authentication on the account you are using to run simulated attacks. In addition, you must be an Office 365 global administrator.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2b152-117">Supporto per l'accesso condizionale saranno presto disponibili.</span><span class="sxs-lookup"><span data-stu-id="2b152-117">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="2b152-118">Per accedere a simulatore di attacco, in sicurezza &amp; centro conformità, scegliere **gestione rischio** \> **simulatore di attacco**.</span><span class="sxs-lookup"><span data-stu-id="2b152-118">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="2b152-119">Prima di iniziare...</span><span class="sxs-lookup"><span data-stu-id="2b152-119">Before you begin...</span></span>

<span data-ttu-id="2b152-120">Verificare che la propria organizzazione soddisfino i requisiti seguenti per simulatore di attacco di tipo:</span><span class="sxs-lookup"><span data-stu-id="2b152-120">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
      
- <span data-ttu-id="2b152-p105">Messaggio di posta elettronica dell'organizzazione è ospitata in Exchange Online. (Simulatore di attacco di tipo non disponibile per i server di posta elettronica locale).</span><span class="sxs-lookup"><span data-stu-id="2b152-p105">Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="2b152-123">Essere un amministratore globale di Office 365</span><span class="sxs-lookup"><span data-stu-id="2b152-123">You are an Office 365 global administrator</span></span>
    
- <span data-ttu-id="2b152-124">L'organizzazione utilizza [l'autenticazione a più fattori per gli utenti di Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="2b152-124">Your organization is using [Multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)</span></span>
 
- <span data-ttu-id="2b152-125">L'organizzazione dispone di [Business Intelligence di rischio di Office 365](office-365-ti.md)con attacco simulatore visibili nella protezione &amp; centro conformità (Vai alla **gestione delle minacce** \> **simulatore di attacco**)</span><span class="sxs-lookup"><span data-stu-id="2b152-125">Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span><br/><span data-ttu-id="2b152-126">![Gestione di rischio - simulatore di attacco](media/ThreatMgmt-AttackSimulator.png)</span><span class="sxs-lookup"><span data-stu-id="2b152-126">![Threat management - Attack Simulator](media/ThreatMgmt-AttackSimulator.png)</span></span>

    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="2b152-127">Attacco spear phishing nome di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="2b152-127">Display name spear-phishing attack</span></span>

<span data-ttu-id="2b152-p106">Il phishing è un termine generico per un ampio gruppo di attacchi classificato come stile attacchi. Questo attacco viene trattata principalmente spear phishing, un attacco più mirato è destinato a un gruppo specifico di singoli utenti o un'organizzazione. In genere, eseguire un attacco personalizzato con alcuni esplorazione delle e utilizzando un nome visualizzato che genera relazione di trust in destinatario, ad esempio un messaggio di posta elettronica è simile a quello proviene da un dirigente all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2b152-p106">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="2b152-p107">Questo attacco è incentrata su che consente di modificare che viene visualizzato il messaggio di origine per la modifica dell'indirizzo di origine e nome visualizzato. Quando gli attacchi di phishing spear esito positivo, cybercriminali accedere alle credenziali degli utenti.</span><span class="sxs-lookup"><span data-stu-id="2b152-p107">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="2b152-133">Per simulare un attacco di spear phishing</span><span class="sxs-lookup"><span data-stu-id="2b152-133">To simulate a spear-phishing attack</span></span>

![Comporre corpo del messaggio di posta elettronica](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="2b152-135">È possibile creare l'editor HTML avanzata direttamente nel campo del **corpo del messaggio di posta elettronica** direttamente o lavorare con origine HTML.</span><span class="sxs-lookup"><span data-stu-id="2b152-135">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>
  
1. <span data-ttu-id="2b152-136">Nella [protezione &amp; centro conformità](https://protection.office.com), scegliere **gestione rischio** \> **simulatore di attacco**.</span><span class="sxs-lookup"><span data-stu-id="2b152-136">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="2b152-137">Specificare un nome significativo campagna per l'attacco o selezionare un modello.</span><span class="sxs-lookup"><span data-stu-id="2b152-137">Specify a meaningful campaign name for the attack or select a template.</span></span> <br/>![Pagina iniziale di phishing](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="2b152-p108">Consente di specificare i destinatari di destinazione. Può trattarsi di singoli utenti o gruppi all'interno dell'organizzazione. Ogni destinatario di destinazione deve essere Online cassetta postale di Exchange in modo che l'attacco abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2b152-p108">Specify the target recipients. This can be individuals or groups in your organization. Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span> <br/>![Selezione dei destinatari](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="2b152-143">Configurare i dettagli di posta elettronica di Phishing.</span><span class="sxs-lookup"><span data-stu-id="2b152-143">Configure the Phishing email details.</span></span> <br/>![Configurare i dettagli di posta elettronica](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/><span data-ttu-id="2b152-p109">La formattazione HTML può essere complessa o base quando la campagna le esigenze. Come formato di posta elettronica HTML, è possibile inserire immagini e testo per il miglioramento believability. È possibile specificare in quali il messaggio ricevuto come appare nel client di posta elettronica destinatario.</span><span class="sxs-lookup"><span data-stu-id="2b152-p109">The HTML formatting can be as complex or basic as your campaign needs. As the email format is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.</span></span>
    
5. <span data-ttu-id="2b152-p110">Specificare il testo del campo **da (Name)** . Questo è il campo che indica il **Nome visualizzato** nel client di posta elettronica destinatario.</span><span class="sxs-lookup"><span data-stu-id="2b152-p110">Specify text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
6. <span data-ttu-id="2b152-p111">Consente di specificare il testo o il campo **da** . Questo è il campo che indica l'indirizzo di posta elettronica del mittente nel client di posta elettronica destinatario.</span><span class="sxs-lookup"><span data-stu-id="2b152-p111">Specify text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client. </span></span><br/><span data-ttu-id="2b152-p112">È possibile immettere uno spazio dei nomi di posta elettronica esistente all'interno dell'organizzazione (in questo modo consentirà l'indirizzo di posta elettronica effettivamente risolvere nel client ricevente semplificazione un modello di protezione estremamente elevata), oppure è possibile immettere un indirizzo di posta elettronica esterno. L'indirizzo di posta elettronica specificato non deve esistere, ma è necessario dopo il formato di un indirizzo SMTP valido, ad esempio user@domainname.extension.</span><span class="sxs-lookup"><span data-stu-id="2b152-p112">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
7. <span data-ttu-id="2b152-p113">Utilizzando il selettore di riepilogo a discesa, selezionare un URL di server di accesso di Phishing che indica il tipo di contenuto che è necessario nell'attacco. URL con temi diversi, vengono forniti da scegliere, ad esempio documenti recapito tecnici, paghe e stipendi e così via. Si tratta in modo efficace l'URL assegnato agli utenti vengono chiesto di fare clic su.</span><span class="sxs-lookup"><span data-stu-id="2b152-p113">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
8. <span data-ttu-id="2b152-p114">Consente di specificare un URL della pagina di destinazione personalizzato. Utilizzando questo verrà reindirizzare gli utenti a un URL specificato alla fine di un attacco. Se si dispone di formazione interni, ad esempio, è possibile specificare che qui.</span><span class="sxs-lookup"><span data-stu-id="2b152-p114">Specify a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.</span></span>
    
9. <span data-ttu-id="2b152-p115">Specificare il testo per il campo **oggetto** . Questo è il campo che indica che il **Nome soggetto** nel client di posta elettronica destinatario.</span><span class="sxs-lookup"><span data-stu-id="2b152-p115">Specify text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
10. <span data-ttu-id="2b152-161">Comporre il **corpo del messaggio di posta elettronica** che riceverà la destinazione.</span><span class="sxs-lookup"><span data-stu-id="2b152-161">Compose the **Email body** that the target will receive.</span></span> <br/><span data-ttu-id="2b152-162">`${username}`Inserisce il nome di destinazioni nel corpo del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="2b152-162">`${username}` inserts the targets name into the Email body.</span></span> <br/><span data-ttu-id="2b152-163">`${loginserverurl}`Inserisce l'URL che si desidera che gli utenti di destinazione fare clic su</span><span class="sxs-lookup"><span data-stu-id="2b152-163">`${loginserverurl}` inserts the URL we want target users to click</span></span> 
    
11. <span data-ttu-id="2b152-p116">Scegliere **Avanti,** quindi **completare** per avviare l'attacco. Messaggio di posta elettronica spear phishing viene recapitato a cassette postali dei destinatari di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2b152-p116">Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="2b152-166">Attacco di tipo spray password</span><span class="sxs-lookup"><span data-stu-id="2b152-166">Password-spray attack</span></span>

<span data-ttu-id="2b152-p117">Un attacco di spray password in un'organizzazione viene utilizzato in genere dopo un attore bad ha acquisito un elenco di utenti validi dal tenant. Attore bad a conoscenza di password comuni che utenti utilizzo. Si tratta di un attacco ampiamente utilizzato come è un attacco di tipo economico esecuzione e più difficili da rilevare di forza bruta approcci.</span><span class="sxs-lookup"><span data-stu-id="2b152-p117">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant. The bad actor knows about common passwords that people use. This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="2b152-170">Questo attacco è incentrata su che consente di specificare una password comune con una base di grandi dimensioni di destinazione di utenti.</span><span class="sxs-lookup"><span data-stu-id="2b152-170">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="2b152-171">Per simulare un attacco spray password</span><span class="sxs-lookup"><span data-stu-id="2b152-171">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="2b152-172">Nella [protezione &amp; centro conformità](https://protection.office.com), scegliere **gestione rischio** \> **simulatore di attacco**.</span><span class="sxs-lookup"><span data-stu-id="2b152-172">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="2b152-173">Specificare un nome significativo campagne un attacco.</span><span class="sxs-lookup"><span data-stu-id="2b152-173">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="2b152-p118">Consente di specificare i destinatari di destinazione. Può trattarsi di singoli utenti o gruppi all'interno dell'organizzazione. Un destinatario destinazione deve essere Online cassetta postale di Exchange in modo che l'attacco abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2b152-p118">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="2b152-p119">Consente di specificare una password da utilizzare per l'attacco. Ad esempio, è una password comune, pertinenti è possibile provare `Fall2017`. Un altro potrebbe essere `Spring2018`, o `Password1`.</span><span class="sxs-lookup"><span data-stu-id="2b152-p119">Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="2b152-180">Scegliere **Fine** per avviare l'attacco.</span><span class="sxs-lookup"><span data-stu-id="2b152-180">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="2b152-181">Attacchi di forza bruta attacco password</span><span class="sxs-lookup"><span data-stu-id="2b152-181">Brute-force password attack</span></span>

<span data-ttu-id="2b152-p120">Un attacco di forza bruta password in un'organizzazione viene utilizzato in genere dopo un attore bad ha acquisito un elenco di utenti chiavi da tenant. Questo attacco è incentrata su cercando un set di password in un singolo account utente.</span><span class="sxs-lookup"><span data-stu-id="2b152-p120">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant. This attack focuses on trying a set of passwords on a single user's account.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="2b152-184">Per simulare un attacco di forza bruta password</span><span class="sxs-lookup"><span data-stu-id="2b152-184">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="2b152-185">Nella [protezione &amp; centro conformità](https://protection.office.com), scegliere **gestione rischio** \> **simulatore di attacco**.</span><span class="sxs-lookup"><span data-stu-id="2b152-185">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="2b152-186">Specificare un nome significativo campagne un attacco.</span><span class="sxs-lookup"><span data-stu-id="2b152-186">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="2b152-p121">Consente di specificare il destinatario. Un destinatario destinazione deve essere Online cassetta postale di Exchange in modo che l'attacco abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2b152-p121">Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="2b152-p122">Specificare una password da utilizzare per l'attacco. A tale scopo, è possibile utilizzare un file di testo (con estensione txt) per l'elenco delle password. Il file di testo non può superare i 10 MB dimensioni file. Utilizzare una password per riga e assicurarsi di includere un ritorno dopo l'ultima password nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2b152-p122">Specify a set of passwords to use for the attack. To do this, you can use a text (.txt) file for your list of passwords. The text file cannot exceed 10 MB in file size. Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>
    
5. <span data-ttu-id="2b152-193">Scegliere **Fine** per avviare l'attacco.</span><span class="sxs-lookup"><span data-stu-id="2b152-193">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="2b152-194">Nuove funzionalità di simulatore di attacco</span><span class="sxs-lookup"><span data-stu-id="2b152-194">New features in Attack Simulator</span></span>

<span data-ttu-id="2b152-p123">Nuove funzionalità vengono aggiunti simulatore di attacco. Tali strumenti comprendono:</span><span class="sxs-lookup"><span data-stu-id="2b152-p123">New features are being added to Attack Simulator. These include:</span></span>
- <span data-ttu-id="2b152-p124">**Creazione di rapporti avanzate**. Sarà in grado di visualizzare i dati, ad esempio l'ora più veloce (o più lento) per aprire un messaggio di posta elettronica simulazione di attacco, l'ora più veloce (o più lento) fare clic su un collegamento nel messaggio e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="2b152-p124">**Advanced reporting capabilities**. You'll be able to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more.</span></span>
- <span data-ttu-id="2b152-p125">**Editor dei modelli di posta elettronica**. È possibile creare un modello di posta elettronica personalizzati e riutilizzabili che è possibile utilizzare per simulazioni attacchi futuri.</span><span class="sxs-lookup"><span data-stu-id="2b152-p125">**Email template editor**. You can create a custom, reusable email template that you can use for future attack simulations.</span></span>

<span data-ttu-id="2b152-201">Visita il sito Web [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) per osservare le novità dello sviluppo di, che cos'è distribuzione e che cos'è già avviato.</span><span class="sxs-lookup"><span data-stu-id="2b152-201">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>



