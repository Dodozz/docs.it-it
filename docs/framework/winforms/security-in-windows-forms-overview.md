---
title: Cenni preliminari sulla sicurezza in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- code access security [Windows Forms], Windows Forms
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms], about security
- access control [Windows Forms], Windows Forms
ms.assetid: 4810dc9f-ea23-4ce1-8ea1-657f0ff1d820
ms.openlocfilehash: a9e90ebc941d07c24f7b14ecf72e5a764bf48d77
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664978"
---
# <a name="security-in-windows-forms-overview"></a>Cenni preliminari sulla sicurezza in Windows Form
Prima del rilascio di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], qualsiasi codice in esecuzione sul computer di un utente aveva gli stessi diritti o le stesse autorizzazioni di accesso alle risorse che aveva un utente del computer. Se ad esempio all'utente era consentito l'accesso al file system o a un database, anche il codice aveva accesso al file system o al database. Anche se ciò può essere accettabile per il codice contenuto negli eseguibili installati esplicitamente dall'utente nel computer locale, non è altrettanto accettabile per quanto riguarda il codice potenzialmente dannoso proveniente da Internet o da una Intranet locale. A questo tipo di codice, infatti, non deve essere consentito l'accesso alle risorse del computer dell'utente senza autorizzazione esplicita.  
  
 In [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] è stata introdotta un'infrastruttura, denominata sicurezza dall'accesso di codice, che consente di differenziare le autorizzazioni, o i diritti, del codice rispetto a quelli dell'utente. Per impostazione predefinita, il codice proveniente da Internet e dalla Intranet può essere eseguito soltanto in un ambiente parzialmente attendibile. Le applicazioni parzialmente attendibili sono soggette a una serie di restrizioni, ad esempio non possono accedere al disco rigido locale né eseguire codice non gestito. Per controllare le risorse a cui il codice può accedere, in [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] viene usata l'identità del codice, ovvero la provenienza, l'eventuale presenza di [Assembly con nome sicuro](../../../docs/framework/app-domains/strong-named-assemblies.md), la presenza di una firma con un certificato e così via.  
  
 Grazie alla tecnologia [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)], usata per la distribuzione delle applicazioni Windows Form, risulta molto più semplice sviluppare applicazioni da eseguire in un ambiente parzialmente attendibile, in un ambiente con attendibilità totale o in un ambiente parzialmente attendibile con autorizzazioni elevate. Usando alcune delle funzionalità offerte da [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)], ad esempio l'elevazione delle autorizzazioni e la distribuzione di applicazioni attendibili, l'applicazione può richiedere automaticamente che l'utente disponga di autorizzazioni elevate o di attendibilità totale.  
  
## <a name="understanding-security-in-the-net-framework"></a>Informazioni sulla sicurezza in .NET Framework  
 La sicurezza dall'accesso di codice consente di assegnare al codice gradi di attendibilità diversi, in base all'origine e ad altri aspetti dell'identità del codice. Per altre informazioni sulle evidenze impiegate da Common Language Runtime per determinare i criteri di sicurezza, vedere [Evidenza](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd(v=vs.100)). Questo strumento consente di proteggere i computer dal codice dannoso e il codice attendibile dai tentativi, sia intenzionali che accidentali, di compromissione della sicurezza. La sicurezza dall'accesso di codice assicura inoltre un controllo maggiore sulle azioni che possono essere eseguite dall'applicazione, poiché consente di assegnare a quest'ultima soltanto le autorizzazioni effettivamente necessarie. Questo tipo di sicurezza ha effetto su tutto il codice gestito destinato a Common Language Runtime, anche se tale codice non effettua un'unica verifica delle autorizzazioni di sicurezza per l'accesso di codice. Per altre informazioni sulla sicurezza in [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], vedere [Concetti principali sulla sicurezza](../../../docs/standard/security/key-security-concepts.md) e [Nozioni fondamentali sulla sicurezza per l'accesso al codice](../../../docs/framework/misc/code-access-security-basics.md).  
  
 Se l'utente esegue un file eseguibile di Windows Form direttamente da un server Web o una condivisione file, il livello di attendibilità concesso all'applicazione dipende dalla posizione in cui si trova il codice e dal modo in cui è stata avviata. Quando viene eseguita, un'applicazione viene automaticamente valutata e riceve un set di autorizzazioni denominato da Common Language Runtime. Per impostazione predefinita, al codice proveniente dal computer locale viene concesso il set di autorizzazioni Completamente attendibile, al codice proveniente da una rete locale viene concesso il set di autorizzazioni Intranet locale e al codice proveniente da Internet viene concesso il set di autorizzazioni Internet.  
  
> [!NOTE]
>  In [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] versione 1.0 Service Pack 1 e Service Pack 2, al gruppo di codice dell'area Internet viene assegnato il set di autorizzazioni Nessuna. In tutte le altre versioni di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], al gruppo di codice dell'area Internet viene assegnato il set di autorizzazioni Internet.  
>   
>  Le autorizzazioni predefinite concesse in ciascuno di questi insiemi sono elencate nell'argomento [Criteri di sicurezza predefiniti](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100)). A seconda delle autorizzazioni ricevute, l'applicazione viene eseguita correttamente o genera un'eccezione di sicurezza.  
>   
>  Molte applicazioni Windows Form verranno distribuite mediante [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]. Gli strumenti impiegati per generare una distribuzione [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] prevedono impostazioni di sicurezza predefinite differenti da quelle illustrate precedentemente. Per altre informazioni, vedere più avanti.  
  
 Poiché i criteri di sicurezza possono essere modificati, è possibile che le autorizzazioni effettive concesse all'applicazione siano diverse dai valori predefiniti. È pertanto possibile che l'applicazione disponga di un'autorizzazione su un computer ma non su un altro.  
  
## <a name="developing-a-more-secure-windows-forms-application"></a>Sviluppo di applicazioni Windows Form più sicure  
 La sicurezza è importante in tutte le fasi di sviluppo delle applicazioni. Iniziare consultando e seguendo le [Linee guida per la generazione di codice sicuro](../../../docs/standard/security/secure-coding-guidelines.md).  
  
 Quindi, decidere se l'applicazione deve essere eseguita in un ambiente completamente attendibile o parzialmente attendibile. L'esecuzione dell'applicazione in un ambiente completamente attendibile rende più semplice l'accesso alle risorse nel computer locale, ma espone l'applicazione e i relativi utenti a rischi di sicurezza maggiori nel caso in cui l'applicazione non sia stata progettata e sviluppata rispettando rigorosamente le linee guida per la generazione di codice sicuro. L'esecuzione dell'applicazione in un ambiente parzialmente attendibile semplifica lo sviluppo di applicazioni sicure e riduce la maggior parte dei rischi, ma richiede una pianificazione più accurata sulle modalità di implementazione di determinate funzionalità.  
  
 Se si sceglie di creare un'applicazione parzialmente attendibile, ovvero con set di autorizzazioni Internet o Intranet locale, occorre decidere come l'applicazione deve comportarsi in tale ambiente. In Windows Form sono disponibili modi alternativi più sicuri per implementare le funzionalità in un ambiente parzialmente attendibile. Alcune parti dell'applicazione, ad esempio l'accesso ai dati, possono essere progettate e scritte in modo differente per i due ambienti (parzialmente attendibile e completamente attendibile). Alcune funzionalità di Windows Form, ad esempio Impostazioni applicazione, sono progettate per funzionare in un ambiente parzialmente attendibile. Per altre informazioni, vedere [Panoramica delle impostazioni delle applicazioni](../../../docs/framework/winforms/advanced/application-settings-overview.md).  
  
 Se l'applicazione richiede più autorizzazioni rispetto a quelle consentite in un ambiente parzialmente attendibile, ma non la si vuole eseguire in un ambiente completamente attendibile, è possibile eseguire l'applicazione in un ambiente parzialmente attendibile effettuando al tempo stesso l'asserzione soltanto delle autorizzazioni aggiuntive necessarie. Se ad esempio si vuole eseguire l'applicazione in un ambiente parzialmente attendibile ma concedere l'accesso in sola lettura a una directory nel file system dell'utente, è possibile richiedere l'autorizzazione <xref:System.Security.Permissions.FileIOPermission> soltanto per tale directory. Se usato correttamente, questo approccio consente di aumentare le capacità dell'applicazione riducendo al minimo i rischi di sicurezza per gli utenti.  
  
 Quando si sviluppa un'applicazione che verrà eseguita in un ambiente parzialmente attendibile, occorre tenere traccia delle autorizzazioni indispensabili all'applicazione e di quelle che potrebbe usare facoltativamente. Quando si conoscono tutte le autorizzazioni, è necessario effettuare una richiesta dichiarativa per le autorizzazioni a livello di applicazione. In questo modo è possibile indicare al runtime di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] le autorizzazioni necessarie all'applicazione e quelle indesiderate. Per altre informazioni sulla richiesta di autorizzazioni, vedere [Richiesta di autorizzazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100)).  
  
 Quando si richiedono autorizzazioni facoltative, è necessario gestire le eccezioni di sicurezza che verranno generate nel caso in cui l'applicazione esegua un'azione che richiede autorizzazioni non concesse. La corretta gestione dell'eccezione <xref:System.Security.SecurityException> assicurerà che l'esecuzione dell'applicazione non venga interrotta. L'eccezione può essere usata dall'applicazione per determinare se è necessario disabilitare una funzionalità per l'utente. Un'applicazione, ad esempio, può disabilitare l'opzione di menu **Salva** se l'autorizzazione necessaria non viene concessa.  
  
 In alcuni casi, è difficile sapere se è stata effettuata l'asserzione di tutte le autorizzazioni appropriate. È possibile, ad esempio, che una chiamata a metodo che a prima vista potrebbe sembrare innocua, a un certo punto dell'esecuzione richieda l'accesso al file system. Se l'applicazione non viene distribuita con tutte le autorizzazioni necessarie, è possibile che l'esecuzione risulti corretta nel proprio computer ma non dopo la distribuzione. Entrambi i [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] SDK e Visual Studio 2005 sono disponibili strumenti per il calcolo delle autorizzazioni richieste da un'applicazione: MT.exe comando dello strumento di riga e la funzionalità Elabora autorizzazioni di Visual Studio, rispettivamente.  
  
 Negli argomenti riportati di seguito vengono illustrate le funzionalità di sicurezza aggiuntive di Windows Form.  
  
|Argomento|Descrizione|  
|-----------|-----------------|  
|-   [File e accesso ai dati più sicuri in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)|Viene descritto come accedere ai file e ai dati in un ambiente parzialmente attendibile.|  
|-   [Stampa più sicura in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)|Viene descritto come accedere alle funzionalità di stampa in un ambiente parzialmente attendibile.|  
|-   [Considerazioni aggiuntive sulla sicurezza in Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)|Viene descritto come modificare le finestre, mediante gli Appunti, ed eseguire chiamate al codice non gestito in un ambiente parzialmente attendibile.|  
  
-  
  
### <a name="deploying-an-application-with-the-appropriate-permissions"></a>Distribuzione di un'applicazione con le autorizzazioni appropriate  
 La distribuzione di un'applicazione Windows Form in un computer client viene in genere eseguita mediante [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)], una tecnologia di distribuzione che consente di descrivere tutti i componenti che devono essere eseguiti dall'applicazione. [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] usa file XML denominati manifesti per descrivere gli assembly e i file che formano l'applicazione nonché le autorizzazioni richieste da quest'ultima.  
  
 In [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] vengono usate due tecnologie per la richiesta di autorizzazioni elevate in un computer client, entrambe basate sull'uso di certificati Authenticode. L'uso dei certificati fornisce una discreta garanzia agli utenti che l'applicazione proviene da una fonte attendibile.  
  
 Queste tecnologie sono descritte nella tabella seguente.  
  
|Tecnologia per autorizzazioni elevate|Descrizione|  
|------------------------------------|-----------------|  
|Elevazione delle autorizzazioni|La prima volta che si esegue l'applicazione, viene visualizzata all'utente una finestra di dialogo di sicurezza di **elevazione delle autorizzazioni** in cui vengono fornite alcune informazioni sull'editore dell'applicazione, in modo che l'utente possa prendere una decisione consapevole sull'assegnazione di altre autorizzazioni all'applicazione.|  
|Distribuzione di applicazioni attendibili|Questa tecnologia richiede che un amministratore di sistema esegua, una sola volta, l'installazione del certificato Authenticode di un'entità di pubblicazione in un computer client. Da quel momento in poi, le eventuali applicazioni firmate con il certificato verranno considerate attendibili e potranno essere eseguite con attendibilità totale nel computer locale senza che venga visualizzata alcuna richiesta all'utente.|  
  
 La tecnologia più adatta dipenderà dallo specifico ambiente di distribuzione. Per altre informazioni, vedere [Scelta di una strategia di distribuzione ClickOnce](/visualstudio/deployment/choosing-a-clickonce-deployment-strategy).  
  
 Per impostazione predefinita [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] le applicazioni distribuite mediante Visual Studio o il [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] strumenti SDK (Mage.exe e MageUI.exe) configurati per l'esecuzione in un computer client con attendibilità totale. Se si vuole distribuire l'applicazione in un ambiente parzialmente attendibile o assegnando soltanto alcune autorizzazioni aggiuntive, sarà necessario modificare le impostazioni predefinite. È possibile farlo con Visual Studio o [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] strumento SDK MageUI.exe quando si configura la distribuzione. Per altre informazioni su come usare MageUI.exe, vedere questa procedura dettagliata: Distribuzione di un'applicazione ClickOnce dalla riga di comando.  Vedere anche [come: Impostare autorizzazioni personalizzate per un'applicazione ClickOnce](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/hafybdaa(v=vs.110)) o [come: Impostare autorizzazioni personalizzate per un'applicazione ClickOnce](/visualstudio/deployment/how-to-set-custom-permissions-for-a-clickonce-application).  
  
 Per altre informazioni sugli aspetti di sicurezza di [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] e sull'elevazione delle autorizzazioni, vedere [Protezione di applicazioni ClickOnce](/visualstudio/deployment/securing-clickonce-applications). Per altre informazioni sulla distribuzione di applicazioni attendibili, vedere [Panoramica della distribuzione di applicazioni attendibili](/visualstudio/deployment/trusted-application-deployment-overview).  
  
### <a name="testing-the-application"></a>Verifica dell'applicazione  
 Se è stata distribuita l'applicazione Windows Forms con Visual Studio, è possibile abilitare il debug in ambiente parzialmente attendibile o un'autorizzazione con restrizioni impostata dall'ambiente di sviluppo.  Vedere anche [come: Eseguire il debug di un'applicazione ClickOnce con autorizzazioni limitate](/visualstudio/deployment/how-to-debug-a-clickonce-application-with-restricted-permissions).  
  
## <a name="see-also"></a>Vedere anche
- [Sicurezza di Windows Form](../../../docs/framework/winforms/windows-forms-security.md)
- [Nozioni fondamentali sulla sicurezza per l’accesso al codice](../../../docs/framework/misc/code-access-security-basics.md)
- [Sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)
- [Panoramica della distribuzione di applicazioni attendibili](/visualstudio/deployment/trusted-application-deployment-overview)
- [Mage.exe (Strumento per la generazione e la modifica di manifesti)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)
- [MageUI.exe (Strumento per la generazione e la modifica di manifesti, client grafico)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
