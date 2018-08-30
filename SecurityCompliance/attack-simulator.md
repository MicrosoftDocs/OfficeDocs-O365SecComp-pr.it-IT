---
title: Simulatore di attacchi in Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/19/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: Informazioni su tre diversi tipi di attacchi cyber che è possibile eseguire utilizzando simulatore di attacco.
ms.openlocfilehash: 364144c0b2f8109c67fb262ce879414088380ebe
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530535"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="d91d5-103">Simulatore di attacchi in Office 365</span><span class="sxs-lookup"><span data-stu-id="d91d5-103">Attack Simulator in Office 365</span></span>

<span data-ttu-id="d91d5-p101">Con attacco simulatore (incluso in [Office 365 rischio Intelligence](office-365-ti.md)), se non è un membro del team di protezione dell'organizzazione, è possibile eseguire scenari di attacco realistico all'interno dell'organizzazione. Ciò consente di identificare e individuare gli utenti vulnerabili prima di un attacco reale un impatto significativo sulla parte inferiore.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p101">With Attack Simulator (included in [Office 365 Threat Intelligence](office-365-ti.md)), if you are a member of your organization's security team, you can run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="d91d5-106">Gli attacchi</span><span class="sxs-lookup"><span data-stu-id="d91d5-106">The Attacks</span></span>

<span data-ttu-id="d91d5-107">Alla versione preview è sono disponibili tre tipi di simulazioni attacco che è possibile eseguire:</span><span class="sxs-lookup"><span data-stu-id="d91d5-107">At preview release we offer three kinds of attack simulations that you can run:</span></span>
  
- [<span data-ttu-id="d91d5-108">Attacco spear phishing nome di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="d91d5-108">Display name spear-phishing attack</span></span>](attack-simulator.md#spearphish)
    
- [<span data-ttu-id="d91d5-109">Attacco di tipo spray password</span><span class="sxs-lookup"><span data-stu-id="d91d5-109">Password-spray attack</span></span>](attack-simulator.md#passwordspray)
    
- [<span data-ttu-id="d91d5-110">Attacchi di forza bruta attacco password</span><span class="sxs-lookup"><span data-stu-id="d91d5-110">Brute-force password attack</span></span>](attack-simulator.md#bruteforce)
    
<span data-ttu-id="d91d5-111">Per un attacco in cui deve essere avviato correttamente, l'account che esegue l'attacco e viene eseguito l'accesso deve utilizzare l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="d91d5-111">For an attack to be successfully launched, the account that is running the attack and logged on must use multi-factor authentication.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d91d5-112">Supporto per l'accesso condizionale saranno presto disponibili.</span><span class="sxs-lookup"><span data-stu-id="d91d5-112">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="d91d5-113">Per accedere a simulatore di attacco, in sicurezza &amp; centro conformità, scegliere **gestione rischio** \> **simulatore di attacco**.</span><span class="sxs-lookup"><span data-stu-id="d91d5-113">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="d91d5-114">Prima di iniziare...</span><span class="sxs-lookup"><span data-stu-id="d91d5-114">Before you begin...</span></span>

<span data-ttu-id="d91d5-115">Verificare che la propria organizzazione soddisfino i requisiti seguenti per simulatore di attacco di tipo:</span><span class="sxs-lookup"><span data-stu-id="d91d5-115">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
  
- <span data-ttu-id="d91d5-116">L'organizzazione dispone di [Business Intelligence di rischio di Office 365](office-365-ti.md)con attacco simulatore visibili nella protezione &amp; centro conformità (Vai alla **gestione delle minacce** \> **simulatore di attacco**)</span><span class="sxs-lookup"><span data-stu-id="d91d5-116">Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span>
    
- <span data-ttu-id="d91d5-p102">Messaggio di posta elettronica dell'organizzazione è ospitata in Exchange Online. (Simulatore di attacco di tipo non disponibile per i server di posta elettronica locale).</span><span class="sxs-lookup"><span data-stu-id="d91d5-p102">Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="d91d5-119">Essere un amministratore globale di Office 365</span><span class="sxs-lookup"><span data-stu-id="d91d5-119">You are an Office 365 global administrator</span></span>
    
- <span data-ttu-id="d91d5-120">L'organizzazione utilizza [l'autenticazione a più fattori per gli utenti di Office 365](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)</span><span class="sxs-lookup"><span data-stu-id="d91d5-120">Your organization is using [Multi-factor authentication for Office 365 users](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)</span></span>
    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="d91d5-121">Attacco spear phishing nome di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="d91d5-121">Display name spear-phishing attack</span></span>

<span data-ttu-id="d91d5-p103">Il phishing è un termine generico per un ampio gruppo di attacchi classificato come stile attacchi. Questo attacco viene trattata principalmente spear phishing, un attacco più mirato è destinato a un gruppo specifico di singoli utenti o un'organizzazione. In genere, eseguire un attacco personalizzato con alcuni esplorazione delle e utilizzando un nome visualizzato che genera relazione di trust in destinatario, ad esempio un messaggio di posta elettronica è simile a quello proviene da un dirigente all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p103">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="d91d5-p104">Questo attacco è incentrata su che consente di modificare che viene visualizzato il messaggio di origine per la modifica dell'indirizzo di origine e nome visualizzato. Quando gli attacchi di phishing spear esito positivo, cybercriminali accedere alle credenziali degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p104">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="d91d5-127">Per simulare un attacco di spear phishing</span><span class="sxs-lookup"><span data-stu-id="d91d5-127">To simulate a spear-phishing attack</span></span>

![Comporre corpo del messaggio di posta elettronica](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="d91d5-p105">È possibile creare l'editor HTML avanzata direttamente nel campo del **corpo del messaggio di posta elettronica** direttamente o lavorare con origine HTML. Esistono due campi importanti per l'inclusione in HTML:</span><span class="sxs-lookup"><span data-stu-id="d91d5-p105">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source. There are two important fields for inclusion in the HTML:</span></span> 
  
1. <span data-ttu-id="d91d5-131">In sicurezza &amp; centro conformità, scegliere **gestione rischio** \> **simulatore di attacco**.</span><span class="sxs-lookup"><span data-stu-id="d91d5-131">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="d91d5-132">Specificare un nome significativo campagna per l'attacco o selezionare un modello.</span><span class="sxs-lookup"><span data-stu-id="d91d5-132">Specify a meaningful campaign name for the attack or select a template.</span></span>
    
    ![Pagina iniziale di phishing](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="d91d5-p106">Consente di specificare i destinatari di destinazione. Può trattarsi di singoli utenti o gruppi all'interno dell'organizzazione. Un destinatario destinazione deve essere Online cassetta postale di Exchange in modo che l'attacco abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p106">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
    ![Selezione dei destinatari](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="d91d5-138">Configurare i dettagli di posta elettronica di Phishing.</span><span class="sxs-lookup"><span data-stu-id="d91d5-138">Configure the Phishing email details.</span></span>
    
    ![Configurare i dettagli di posta elettronica](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)
  
    <span data-ttu-id="d91d5-p107">La formattazione HTML può essere complessa o base quando la campagna le esigenze. Come HTML, è possibile inserire immagini e testo per il miglioramento believability. È possibile specificare in quali il messaggio ricevuto come appare nel client di posta elettronica destinatario.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p107">The HTML formatting can be as complex or basic as your campaign needs. As it is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.</span></span>
    
1. <span data-ttu-id="d91d5-p108">Immettere il testo del campo **da (Name)** . Questo è il campo che indica il **Nome visualizzato** nel client di posta elettronica destinatario.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p108">Enter text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
2. <span data-ttu-id="d91d5-p109">Immettere il testo o il campo **da** . Questo è il campo che indica l'indirizzo di posta elettronica del mittente nel client di posta elettronica destinatario.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p109">Enter text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="d91d5-p110">È possibile immettere uno spazio dei nomi di posta elettronica esistente all'interno dell'organizzazione (in questo modo consentirà l'indirizzo di posta elettronica effettivamente risolvere nel client ricevente semplificazione un modello di protezione estremamente elevata), oppure è possibile immettere un indirizzo di posta elettronica esterno. L'indirizzo di posta elettronica specificato non deve esistere, ma è necessario dopo il formato di un indirizzo SMTP valido, ad esempio user@domainname.extension.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p110">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
3. <span data-ttu-id="d91d5-p111">Utilizzando il selettore di riepilogo a discesa, selezionare un URL di server di accesso di Phishing che indica il tipo di contenuto che è necessario nell'attacco. URL con temi diversi, vengono forniti da scegliere, ad esempio documenti recapito tecnici, paghe e stipendi e così via. Si tratta in modo efficace l'URL assegnato agli utenti vengono chiesto di fare clic su.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p111">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
4. <span data-ttu-id="d91d5-p112">Immettere l'URL di una pagina di destinazione personalizzato. Utilizzando questo verrà reindirizzare gli utenti a un URL specificato alla fine di un attacco. Se si dispone di formazione interni, ad esempio, è possibile specificare che qui.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p112">Enter a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.</span></span>
    
5. <span data-ttu-id="d91d5-p113">Immettere il testo nel campo **oggetto** . Questo è il campo che indica che il **Nome soggetto** nel client di posta elettronica destinatario.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p113">Enter text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
5. <span data-ttu-id="d91d5-156">Comporre il **corpo del messaggio di posta elettronica** che riceverà la destinazione.</span><span class="sxs-lookup"><span data-stu-id="d91d5-156">Compose the **Email body** that the target will receive.</span></span> 
  
 <span data-ttu-id="d91d5-157">**${username}** inserisce il nome di destinazioni nel corpo del messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d91d5-157">**${username}** inserts the targets name into the Email body</span></span> 
  
 <span data-ttu-id="d91d5-158">**${loginserverurl}** inserisce l'URL che si desidera che gli utenti di destinazione fare clic su</span><span class="sxs-lookup"><span data-stu-id="d91d5-158">**${loginserverurl}** inserts the URL we want target users to click</span></span> 
    
6. <span data-ttu-id="d91d5-p114">Scegliere **Avanti,** quindi **completare** per avviare l'attacco. Messaggio di posta elettronica spear phishing viene recapitato a cassette postali dei destinatari di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p114">Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="d91d5-161">Attacco di tipo spray password</span><span class="sxs-lookup"><span data-stu-id="d91d5-161">Password-spray attack</span></span>

<span data-ttu-id="d91d5-p115">Un attacco di spray password in un'organizzazione viene utilizzato in genere dopo un attore bad correttamente i valori enumerati un elenco di utenti validi dal tenant, utilizzando le proprie conoscenze di password comuni utilizzati. È utilizzata frequentemente come è un attacco di tipo economico per l'esecuzione e più difficili da rilevare di forza bruta approcci.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p115">A password spray attack against an organization is typically used after a bad actor has successfully enumerated a list of valid users from the tenant, utilizing their knowledge of common passwords used. It is utilized widely as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="d91d5-164">Questo attacco è incentrata su che consente di specificare una password comune con una base di grandi dimensioni di destinazione di utenti.</span><span class="sxs-lookup"><span data-stu-id="d91d5-164">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="d91d5-165">Per simulare un attacco spray password</span><span class="sxs-lookup"><span data-stu-id="d91d5-165">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="d91d5-166">In sicurezza &amp; centro conformità, scegliere **gestione rischio** \> **simulatore di attacco**.</span><span class="sxs-lookup"><span data-stu-id="d91d5-166">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="d91d5-167">Specificare un nome significativo campagne un attacco.</span><span class="sxs-lookup"><span data-stu-id="d91d5-167">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="d91d5-p116">Consente di specificare i destinatari di destinazione. Può trattarsi di singoli utenti o gruppi all'interno dell'organizzazione. Un destinatario destinazione deve essere Online cassetta postale di Exchange in modo che l'attacco abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p116">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="d91d5-p117">Consente di specificare una password da utilizzare per l'attacco. Ad esempio, è una password comune, pertinenti è possibile provare `Fall2017`. Un altro potrebbe essere `Spring2018`, o `Password1`.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p117">Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="d91d5-174">Scegliere **Fine** per avviare l'attacco.</span><span class="sxs-lookup"><span data-stu-id="d91d5-174">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="d91d5-175">Attacchi di forza bruta attacco password</span><span class="sxs-lookup"><span data-stu-id="d91d5-175">Brute-force password attack</span></span>

<span data-ttu-id="d91d5-p118">Un attacco di forza bruta password in un'organizzazione viene utilizzato in genere dopo un attore bad correttamente i valori enumerati un elenco di utenti chiavi da tenant. Questo attacco è incentrata su che consente di specificare un set di password con un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p118">A brute-force password attack against an organization is typically used after a bad actor has successfully enumerated a list of key users from the tenant. This attack focuses on letting you specify a set of passwords against a single user.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="d91d5-178">Per simulare un attacco di forza bruta password</span><span class="sxs-lookup"><span data-stu-id="d91d5-178">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="d91d5-179">In sicurezza &amp; centro conformità, scegliere **gestione rischio** \> **simulatore di attacco**.</span><span class="sxs-lookup"><span data-stu-id="d91d5-179">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="d91d5-180">Specificare un nome significativo campagne un attacco.</span><span class="sxs-lookup"><span data-stu-id="d91d5-180">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="d91d5-p119">Consente di specificare il destinatario. Un destinatario destinazione deve essere Online cassetta postale di Exchange in modo che l'attacco abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p119">Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="d91d5-p120">Specificare una password da utilizzare per l'attacco. Ad esempio, è una password comune, pertinenti è possibile provare `Fall2017`. Un altro potrebbe essere `Spring2018`, o `Password1`.</span><span class="sxs-lookup"><span data-stu-id="d91d5-p120">Specify a set of passwords to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="d91d5-186">Scegliere **Fine** per avviare l'attacco.</span><span class="sxs-lookup"><span data-stu-id="d91d5-186">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="d91d5-187">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d91d5-187">Related topics</span></span>

[<span data-ttu-id="d91d5-188">Office 365 Threat Intelligence</span><span class="sxs-lookup"><span data-stu-id="d91d5-188">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  

