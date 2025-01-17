---
title: Creazione di assembly satellite per applicazioni desktop
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deploying applications [.NET Framework], resources
- resource files, deploying
- hub-and-spoke resource deployment model
- resource files, packaging
- application resources, packaging
- public keys, obtaining
- satellite assemblies
- assemblies [.NET Framework], signing
- application resources, deploying
- Al.exe
- GAC (global assembly cache), satellite assemblies
- Assembly Linker
- directory locations for satellite assemblies
- global assembly cache, satellite assemblies
- packaging application resources
- compiling satellite assemblies
- re-signing assemblies
ms.assetid: 8d5c6044-2919-41d2-8321-274706b295ac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 843b61257229bb3bf8c3852554f19c34dccc7496
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592357"
---
# <a name="creating-satellite-assemblies-for-desktop-apps"></a>Creazione di assembly satellite per applicazioni desktop
I file di risorse svolgono un ruolo centrale nelle applicazioni localizzate. Questi file consentono a un'applicazione di visualizzare stringhe, immagini e altri dati nella lingua dell'utente e con le impostazioni cultura di questo, fornendo anche dati alternativi per i casi in cui non siano disponibili risorse per la lingua o le impostazioni cultura dell'utente. Per individuare e recuperare risorse localizzate, .NET Framework usa un modello hub e spoke. L'hub è l'assembly principale che contiene il codice eseguibile non localizzabile e le risorse di un singolo set di impostazioni cultura, denominate impostazioni cultura neutre o predefinite. Le impostazioni cultura predefinite sono le impostazioni di fallback per l'applicazione, usate quando non sono disponibili risorse localizzate. Per designare le impostazioni cultura predefinite dell'applicazione, si usa l'attributo <xref:System.Resources.NeutralResourcesLanguageAttribute>. Ogni spoke si connette a un assembly satellite contenente le risorse relative a impostazioni cultura specifiche, ma non contiene codice. Poiché gli assembly satellite non fanno parte dell'assembly principale, è possibile aggiornare o sostituire facilmente le risorse corrispondenti a impostazioni cultura specifiche senza sostituire l'assembly principale dell'applicazione.  
  
> [!NOTE]
>  Le risorse delle impostazioni cultura predefinite di un'applicazione possono anche essere archiviate in un assembly satellite. A tale scopo, si assegna all'attributo <xref:System.Resources.NeutralResourcesLanguageAttribute> un valore di <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType>.  
  
## <a name="satellite-assembly-name-and-location"></a>Posizione e nome dell'assembly satellite  
 Requisito del modello hub e spoke è che le risorse vengano inserite in posizioni specifiche perché possano essere individuate e usate con facilità. Se le risorse non vengono compilate e denominate come previsto oppure se non vengono inserite nelle posizioni corrette, Common Language Runtime non è in grado di individuarle e usa le impostazioni cultura predefinite. Lo strumento Gestione risorse di .NET Framework, rappresentato da un oggetto <xref:System.Resources.ResourceManager>, viene usato per accedere automaticamente alle risorse localizzate. Gestione risorse richiede quanto segue:  
  
- Un assembly satellite singolo deve includere tutte le risorse relative a impostazioni cultura particolari. In altre parole, è necessario compilare più file con estensione txt o resx in un unico file binario con estensione resources.  
  
- Nella directory dell'applicazione deve esistere una sottodirectory separata per ognuna delle impostazioni cultura localizzate. In tali sottodirectory devono essere archiviate le risorse delle rispettive impostazioni cultura. Il nome della sottodirectory deve essere lo stesso delle impostazioni cultura. In alternativa, è possibile archiviare gli assembly satellite nella Global Assembly Cache. In questo caso, il componente delle informazioni delle impostazioni cultura del nome sicuro dell'assembly deve indicare le impostazioni cultura corrispondenti. Vedere la sezione [Installazione di assembly satellite nella Global Assembly Cache](#SN) più avanti in questo argomento.  
  
    > [!NOTE]
    >  Se l'applicazione include risorse per impostazioni cultura secondarie, inserire le impostazioni cultura secondarie in una sottodirectory separata all'interno della directory dell'applicazione. Non inserire impostazioni cultura secondarie all'interno di sottodirectory della directory delle impostazioni cultura principali.  
  
- L'assembly satellite deve avere lo stesso nome dell'applicazione e deve usare l'estensione di file ".resources.dll". Se ad esempio un'applicazione è denominata Example.exe, il nome di ogni assembly satellite deve essere Example.resources.dll. Si noti che il nome dell'assembly satellite non indica le impostazioni cultura dei file di risorse corrispondenti. L'assembly satellite, tuttavia, viene visualizzato in una directory che specifica le impostazioni cultura.  
  
- Le informazioni sulle impostazioni cultura dell'assembly satellite devono essere incluse nei metadati dell'assembly. Per archiviare il nome delle impostazioni cultura nei metadati dell'assembly satellite, specificare l'opzione `/culture` quando si incorporano le risorse nell'assembly satellite tramite [Assembly Linker](../../../docs/framework/tools/al-exe-assembly-linker.md).  
  
 La figura seguente illustra una struttura di directory di esempio e i requisiti relativi alla posizione per le applicazioni che non si intende installare nella [Global Assembly Cache](../../../docs/framework/app-domains/gac.md). Gli elementi con estensione txt e resources non verranno forniti con l'applicazione finale. Questi sono file di risorse intermedi usati per creare gli assembly di risorse satellite finali. In questo esempio è possibile sostituire il file con estensione resx per i file con estensione txt. Per altre informazioni, vedere [Creazione del pacchetto e distribuzione delle risorse](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md). 
 
 L'immagine seguente mostra la directory degli assembly satellite:
  
 ![una directory di assembly satellite con sottodirectory di impostazioni cultura localizzate.](./media/creating-satellite-assemblies-for-desktop-apps/satellite-assembly-directory.gif)
  
## <a name="compiling-satellite-assemblies"></a>compilazione di assembly satellite  
 Per compilare file di testo o il file XML (con estensione resx) contenente risorse per file binari con estensione resources, si usa il [generatore di file di risorse (Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md). Si usa quindi [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) per compilare i file con estensione resources in assembly satellite. Al.exe crea un assembly dai file con estensione resources specificati. Gli assembly satellite possono contenere solo risorse. Non possono contenere codice eseguibile.  
  
 Il comando Al.exe seguente crea un assembly satellite per l'applicazione `Example` dal file di risorse strings.de.resources tedesco.  
  
```console
al -target:lib -embed:strings.de.resources -culture:de -out:Example.resources.dll  
```  
  
 Il comando Al.exe seguente crea anche un assembly satellite per l'applicazione `Example` dal file strings.de.resources. L'opzione **/template** fa sì che l'assembly satellite erediti tutti i metadati dell'assembly tranne le informazioni relative alle impostazioni cultura dell'assembly padre (Example. dll).  
  
```console
al -target:lib -embed:strings.de.resources -culture:de -out:Example.resources.dll -template:Example.dll  
```  
  
 Nella tabella seguente vengono descritte in modo più dettagliato le opzioni di Al.exe usate in questi comandi.  
  
|Opzione|Description|  
|------------|-----------------|  
|**-target:** lib|Specifica che l'assembly satellite deve essere compilato in un file di libreria con estensione dll. Poiché un assembly satellite non contiene codice eseguibile e non rappresenta l'assembly principale dell'applicazione, è necessario salvare gli assembly satellite come DLL.|  
|**-embed:** strings.de.resources|Specifica il nome del file di risorse da incorporare quando Al.exe compila l'assembly. È possibile incorporare più file con estensione resources in un assembly satellite. Se si segue il modello hub e spoke, però, è necessario compilare un assembly satellite per ognuna delle impostazioni cultura. È tuttavia possibile creare file con estensione resources separati per le stringhe e gli oggetti.|  
|**-culture:** de|Specifica le impostazioni cultura della risorsa da compilare. Common Language Runtime usa queste informazioni durante la ricerca delle risorse per impostazioni cultura specifiche. Se si omette questa opzione, Al.exe compila comunque la risorsa, ma il runtime non sarà in grado di trovarla quando un utente la richiederà.|  
|**-out:** Example.resources.dll|Specifica il nome del file di output. Il nome deve seguire lo standard di denominazione *nomeBase*.resources.*estensione*, dove *nomeBase* è il nome dell'assembly principale ed *estensione* è un'estensione di file valida, ad esempio dll. Si noti che il runtime non è in grado di determinare le impostazioni cultura di un assembly satellite in base al nome del file di output. Per specificare tali impostazioni è necessario usare l'opzione **/culture**.|  
|**-template:** Example.dll|Specifica l'assembly dal quale l'assembly satellite deve ereditare tutti i metadati, ad eccezione del campo relativo alle impostazioni cultura. Questa opzione influisce sugli assembly satellite solo se si specifica un assembly con un [nome sicuro](../../../docs/framework/app-domains/strong-named-assemblies.md).|  
  
 Per l'elenco completo delle opzioni disponibili con Al.exe, vedere [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md).  
  
## <a name="satellite-assemblies-an-example"></a>Assembly satellite: Esempio  
 Di seguito è riportato un semplice esempio di tipo "Hello world" che visualizza una finestra di messaggio contenente un saluto localizzato. L'esempio include le risorse per le impostazioni cultura inglesi (Stati Uniti), francesi (Francia) e russe (Russia). Le impostazioni cultura inglesi sono le impostazioni cultura di fallback. Per creare l'esempio, eseguire le operazioni seguenti:  
  
1. Creare un file di risorse denominato Greeting.resx o Greeting.txt che deve contenere le risorse per le impostazioni cultura predefinite. Salvare in questo file un'unica stringa denominata `HelloString` il cui valore sia "Hello world!" .  
  
2. Per impostare le impostazioni cultura inglesi (en) come predefinite per l'applicazione, aggiungere l'attributo <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=nameWithType> seguente al file AssemblyInfo dell'applicazione o al file di codice sorgente principale che verrà compilato nell'assembly principale dell'applicazione.  
  
     [!code-csharp[Conceptual.Resources.Locating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.locating/cs/assemblyinfo.cs#2)]
     [!code-vb[Conceptual.Resources.Locating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.locating/vb/assemblyinfo.vb#2)]  
  
3. Aggiungere all'applicazione il supporto per le impostazioni cultura aggiuntive (en-US, fr-FR e ru-RU) come segue:  
  
    - Per supportare le impostazioni cultura en-US, cioè Inglese (Stati Uniti), creare un file di risorse denominato Greeting.en-US.resx o Greeting.en-US.txt e salvare al suo interno una sola stringa denominata `HelloString` il cui valore sia "Hi world!".  
  
    - Per supportare le impostazioni cultura fr-FR, cioè Francese (Francia), creare un file di risorse denominato Greeting.fr-FR.resx o Greeting.fr-FR.txt e salvare al suo interno una sola stringa denominata `HelloString` il cui valore sia "Salut tout le monde!".  
  
    - Per supportare le impostazioni cultura ru-RU, cioè Russo (Russia), creare un file di risorse denominato Greeting.ru-RU.resx o Greeting.ru-RU.txt e salvare al suo interno una sola stringa denominata `HelloString` il cui valore sia "Всем привет!".  
  
4. Usare [Resgen.exe](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) per compilare ogni file di risorse testo o XML in un file con estensione resources binario. L'output è un set di file con lo stesso nome file radice dei file con estensione resx o txt, ma con estensione resources. Se si crea l'esempio con Visual Studio, il processo di compilazione viene gestito automaticamente. Se non si usa Visual Studio, eseguire i comandi seguenti per compilare i file con estensione resx in file con estensione resources:  
  
    ```console
    resgen Greeting.resx  
    resgen Greeting.en-us.resx  
    resgen Greeting.fr-FR.resx  
    resgen Greeting.ru-RU.resx  
    ```  
  
     Se le risorse sono contenute in file di testo anziché in file XML, sostituire l'estensione resx con l'estensione txt.  
  
5. Compilare il codice sorgente seguente con le risorse per le impostazioni cultura predefinite nell'assembly principale dell'applicazione:  
  
    > [!IMPORTANT]
    >  Se per creare l'esempio si usa la riga di comando anziché Visual Studio, è necessario modificare la chiamata al costruttore della classe <xref:System.Resources.ResourceManager> come segue: `ResourceManager rm = new ResourceManager("Greetings", typeof(Example).Assembly);`  
  
     [!code-csharp[Conceptual.Resources.Locating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.locating/cs/program.cs#1)]
     [!code-vb[Conceptual.Resources.Locating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.locating/vb/module1.vb#1)]  
  
     Se l'applicazione è denominata Example e si esegue la compilazione dalla riga di comando, il comando per il compilatore C# è:  
  
    ```console  
    csc Example.cs -res:Greeting.resources  
    ```  
  
     Per il compilatore Visual Basic il comando corrispondente è:  
  
    ```console  
    vbc Example.vb -res:Greeting.resources  
    ```  
  
6. Creare una sottodirectory nella directory principale dell'applicazione per ognuna delle impostazioni cultura localizzate supportate dall'applicazione. È necessario creare le sottodirectory en-US, fr-FR e ru-RU. Visual Studio crea queste sottodirectory automaticamente nell'ambito del processo di compilazione.  
  
7. Incorporare i singoli file con estensione resources specifici di ognuna delle impostazioni cultura in assembly satellite e salvarli nella directory appropriata. Il comando per eseguire questa operazione per ogni file con estensione resources è:  
  
    ```console
    al -target:lib -embed:Greeting.culture.resources -culture:culture -out:culture\Example.resources.dll  
    ```  
  
     dove *culture* è il nome delle impostazioni cultura le cui risorse sono contenute dall'assembly satellite. Visual Studio gestisce questo processo automaticamente.  
  
 È quindi possibile eseguire l'esempio. Questo effettua una selezione casuale tra le impostazioni cultura supportate, definisce le impostazioni cultura selezionate come correnti e visualizza il saluto localizzato.  
  
<a name="SN"></a>   
## <a name="installing-satellite-assemblies-in-the-global-assembly-cache"></a>Installazione di assembly satellite nella Global Assembly Cache  
 Invece di installare gli assembly in una sottodirectory locale dell'applicazione, è possibile installarli nella Global Assembly Cache. Ciò è particolarmente utile se alcuni assembly di librerie di classi e di risorse di librerie di classi vengono usati da più applicazioni.  
  
 L'installazione di assembly nella Global Assembly Cache richiede che gli assembly abbiano nomi sicuri. Gli assembly con nomi sicuri, firmati con una coppia di chiavi pubblica/privata valida, contengono informazioni sulla versione usate dal runtime allo scopo di determinare l'assembly da usare per soddisfare una richiesta di associazione. Per altre informazioni sui nomi sicuri e sul controllo delle versioni, vedere [Controllo delle versioni degli assembly](../../../docs/framework/app-domains/assembly-versioning.md). Per altre informazioni sui nomi sicuri, vedere [Assembly con nomi sicuri](../../../docs/framework/app-domains/strong-named-assemblies.md).  
  
 Quando si sviluppa un'applicazione, è improbabile che si possa accedere alla coppia di chiavi pubblica/privata finale. Per installare un assembly satellite nella Global Assembly Cache e assicurarsi che funzioni come previsto, è possibile usare la cosiddetta tecnica del ritardo della firma. Quando si ritarda la firma di un assembly, al momento della compilazione viene riservato spazio nel file per la firma con nome sicuro. La firma effettiva viene posticipata al momento in cui la coppia di chiavi pubblica/privata finale è disponibile. Per altre informazioni sul ritardo della firma, vedere [Ritardo della firma di un assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).  
  
### <a name="obtaining-the-public-key"></a>Ottenere la chiave pubblica  
 Per ritardare la firma di un assembly, è necessario avere accesso alla chiave pubblica. È possibile ottenere la chiave pubblica reale dall'organizzazione della società che eventualmente effettuerà la firma oppure creare una chiave pubblica con lo [strumento Nome sicuro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md).  
  
 Il comando Sn.exe seguente crea una coppia di chiavi pubblica/privata di test. L'opzione **-k** specifica che Sn.exe deve creare una nuova coppia di chiavi e salvarla in un file denominato TestKeyPair.snk.  
  
```console
sn –k TestKeyPair.snk   
```  
  
 È possibile estrarre la chiave pubblica dal file che contiene la coppia di chiavi di test. Il comando seguente estrae la chiave pubblica da TestKeyPair.snk e lo salva in PublicKey.snk:  
  
```console
sn –p TestKeyPair.snk PublicKey.snk  
```  
  
### <a name="delay-signing-an-assembly"></a>Ritardo della firma di un assembly  
 Dopo aver ottenuto o creato la chiave pubblica, si usa [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) per compilare l'assembly e specificare il ritardo della firma.  
  
 Il comando Al.exe seguente crea un assembly satellite con nome sicuro per la DLL StringLibrary dell'applicazione dal file di risorse strings.ja.resources:  
  
```console 
al -target:lib -embed:strings.ja.resources -culture:ja -out:StringLibrary.resources.dll -delay+ -keyfile:PublicKey.snk  
```  
  
 L'opzione **-delay+** specifica che Assembly Linker deve ritardare la firma dell'assembly. L'opzione **-keyfile** specifica il nome del file di chiave che contiene la chiave pubblica da usare per ritardare la firma dell'assembly.  
  
### <a name="re-signing-an-assembly"></a>Nuova firma di un assembly  
 Prima di distribuire l'applicazione, è necessario firmare nuovamente l'assembly satellite con ritardo della firma con la coppia di chiavi reale. A tale scopo, è possibile usare Sn.exe.  
  
 Il comando Sn.exe seguente firma StringLibrary.resources.dll con la coppia di chiavi archiviata nel file RealKeyPair.snk. L'opzione **-R** specifica che un assembly firmato in precedenza deve essere firmato nuovamente o che un assembly con ritardo della firma deve essere firmato.  
  
```console
sn –R StringLibrary.resources.dll RealKeyPair.snk   
```  
  
### <a name="installing-a-satellite-assembly-in-the-global-assembly-cache"></a>Installazione di un assembly satellite nella Global Assembly Cache  
 Durante la ricerca di risorse nell'ambito del processo di fallback delle risorse, il runtime prima cerca nella [Global Assembly Cache](../../../docs/framework/app-domains/gac.md). Per altre informazioni, vedere la sezione "Processo di fallback delle risorse" dell'argomento [Creazione del pacchetto e distribuzione delle risorse](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md). Non appena un assembly satellite viene firmato con un nome sicuro, può essere installato nella Global Assembly Cache tramite lo [strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).  
  
 Il comando Gacutil.exe seguente installa StringLibrary.resources.dll nella Global Assembly Cache:  
  
```console
gacutil -i:StringLibrary.resources.dll  
```  
  
 L'opzione **/i** specifica che Gacutil.exe deve installare l'assembly specificato nella Global Assembly Cache. Dopo l'installazione dell'assembly satellite nella cache, le risorse in esso contenute diventano disponibili per tutte le applicazioni progettate per l'uso dell'assembly satellite.  
  
### <a name="resources-in-the-global-assembly-cache-an-example"></a>Risorse nella Global Assembly Cache: Esempio  
 L'esempio seguente usa un metodo di una libreria di classi .NET Framework per estrarre e restituire un messaggio di saluto localizzato contenuto in un file di risorse. La libreria e le relative risorse sono registrate nella Global Assembly Cache. L'esempio include risorse per le impostazioni cultura inglesi (Stati Uniti), francesi (Francia), russe (Russia) e inglesi. Le impostazioni cultura predefinite corrispondono a quelle inglesi e le risorse corrispondenti sono archiviate nell'assembly principale. All'inizio dell'esempio viene impostato il ritardo della firma della libreria e dei relativi assembly con una chiave pubblica. Questi vengono quindi firmati di nuovo con una coppia di chiavi pubblica/privata. Per creare l'esempio, eseguire le operazioni seguenti:  
  
1. Se non si usa Visual Studio, creare una coppia di chiavi pubblica/privata denominata ResKey.snk tramite il comando dello [strumento Nome sicuro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) seguente:  
  
    ```console
    sn –k ResKey.snk  
    ```  
  
     Se si usa Visual Studio, generare il file di chiave tramite la scheda **Firma** della finestra di dialogo **Proprietà** del progetto.  
  
2. Usare il comando dello [strumento Nome sicuro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) seguente per creare un file di chiave pubblica denominato PublicKey.snk:  
  
    ```console
    sn –p ResKey.snk PublicKey.snk  
    ```  
  
3. Creare un file di risorse denominato Strings.resx o Greeting.txt che contenga le risorse per le impostazioni cultura predefinite. Archiviare in questo file un'unica stringa denominata `Greeting` il cui valore sia "How do you do?" .  
  
4. Per impostare "en" come impostazioni cultura predefinite dell'applicazione, aggiungere l'attributo <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=nameWithType> seguente al file AssemblyInfo dell'applicazione o al file di codice sorgente principale che verrà compilato nell'assembly principale dell'applicazione:  
  
     [!code-csharp[Conceptual.Resources.Satellites#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/stringlibrary.cs#2)]
     [!code-vb[Conceptual.Resources.Satellites#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/stringlibrary.vb#2)]  
  
5. Aggiungere all'applicazione il supporto per le impostazioni cultura aggiuntive (en-US, fr-FR e ru-RU) come segue:  
  
    - Per supportare le impostazioni cultura "en-US", cioè Inglese (Stati Uniti), creare un file di risorse denominato Strings.en-US.resx o Strings.en-US.txt e salvare al suo interno una sola stringa denominata `Greeting` il cui valore sia "Hello!".  
  
    - Per supportare le impostazioni cultura "fr-FR", cioè Francese (Francia), creare un file di risorse denominato Strings.fr-FR.resx o Strings.fr-FR.txt e salvare al suo interno una sola stringa denominata `Greeting` il cui valore sia "Bonjour!".  
  
    - Per supportare le impostazioni cultura "ru-RU", cioè Russo (Russia), creare un file di risorse denominato Strings.ru-RU.resx o Strings.ru-RU.txt e salvare al suo interno una sola stringa denominata `Greeting` il cui valore sia "Привет!".  
  
6. Usare [Resgen.exe](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) per compilare ogni file di risorse testo o XML in un file con estensione resources binario. L'output è un set di file con lo stesso nome file radice dei file con estensione resx o txt, ma con estensione resources. Se si crea l'esempio con Visual Studio, il processo di compilazione viene gestito automaticamente. Se non si usa Visual Studio, eseguire il comando seguente per compilare i file con estensione resx in file con estensione resources:  
  
    ```console
    resgen filename  
    ```  
  
     dove *filename* rappresenta il percorso facoltativo, il nome file e l'estensione del file resx o di testo.  
  
7. Compilare il codice sorgente seguente per StringLibrary.vb o StringLibrary.cs con le risorse per le impostazioni cultura predefinite in un assembly con ritardo della firma denominato StringLibrary.dll:  
  
    > [!IMPORTANT]
    >  Se per creare l'esempio si usa la riga di comando anziché Visual Studio, è necessario modificare la chiamata al costruttore della classe <xref:System.Resources.ResourceManager> in `ResourceManager rm = new ResourceManager("Strings",` `typeof(Example).Assembly);`.  
  
     [!code-csharp[Conceptual.Resources.Satellites#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/stringlibrary.cs#1)]
     [!code-vb[Conceptual.Resources.Satellites#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/stringlibrary.vb#1)]  
  
     La riga di comando per il compilatore C# è:  
  
    ```console
    csc -t:library -resource:Strings.resources -delaysign+ -keyfile:publickey.snk StringLibrary.cs  
    ```  
  
     Per il compilatore Visual Basic il comando corrispondente è:  
  
    ```console  
    vbc -t:library -resource:Strings.resources -delaysign+ -keyfile:publickey.snk StringLibrary.vb  
    ```  
  
8. Creare una sottodirectory nella directory principale dell'applicazione per ognuna delle impostazioni cultura localizzate supportate dall'applicazione. È necessario creare le sottodirectory en-US, fr-FR e ru-RU. Visual Studio crea queste sottodirectory automaticamente nell'ambito del processo di compilazione. Poiché tutti gli assembly satellite hanno lo stesso nome file, le sottodirectory vengono usate per archiviare gli assembly satellite specifici delle impostazioni cultura fino a quando non sono firmati con una coppia di chiavi pubblica/privata.  
  
9. Incorporare i singoli file con estensione resources specifici di ognuna delle impostazioni cultura in assembly satellite con ritardo della firma e salvarli nella directory appropriata. Il comando per eseguire questa operazione per ogni file con estensione resources è:  
  
    ```console
    al -target:lib -embed:Strings.culture.resources -culture:culture -out:culture\StringLibrary.resources.dll -delay+ -keyfile:publickey.snk  
    ```  
  
     dove *culture* è il nome delle impostazioni cultura. In questo esempio i nomi delle impostazioni cultura sono en-US, fr-FR e ru-RU.  
  
10. Firmare nuovamente StringLibrary.dll tramite lo [strumento Nome sicuro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) come indicato di seguito:  
  
    ```console
    sn –R StringLibrary.dll RealKeyPair.snk  
    ```  
  
11. Firmare nuovamente i singoli assembly satellite. A tale scopo, usare lo [strumento Nome sicuro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) come indicato di seguito per ogni assembly satellite:  
  
    ```console
    sn –R StringLibrary.resources.dll RealKeyPair.snk  
    ```  
  
12. Registrare StringLibrary.dll e ognuno dei relativi assembly satellite nella Global Assembly Cache tramite il comando seguente:  
  
    ```console
    gacutil -i filename  
    ```  
  
     dove *filename* rappresenta il nome del file da registrare.  
  
13. Se si usa Visual Studio, creare un nuovo progetto di **applicazione console** denominato `Example`, aggiungervi un riferimento a StringLibrary.dll e il codice sorgente seguente e quindi eseguire la compilazione.  
  
     [!code-csharp[Conceptual.Resources.Satellites#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/example.cs#3)]
     [!code-vb[Conceptual.Resources.Satellites#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/example.vb#3)]  
  
     Per eseguire la compilazione dalla riga di comando, per il compilatore C# usare il comando seguente:  
  
    ```console
    csc Example.cs -r:StringLibrary.dll   
    ```  
  
     La riga di comando per il compilatore Visual Basic è:  
  
    ```console
    vbc Example.vb -r:StringLibrary.dll   
    ```  
  
14. Eseguire Example.exe.  
  
## <a name="see-also"></a>Vedere anche

- [Creazione del pacchetto e distribuzione delle risorse](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Ritardo della firma di un assembly](../../../docs/framework/app-domains/delay-sign-assembly.md)
- [Al.exe (Assembly Linker)](../../../docs/framework/tools/al-exe-assembly-linker.md)
- [Sn.exe (strumento Nome sicuro)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)
- [Gacutil.exe (strumento Global Assembly Cache)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
- [Risorse nelle applicazioni desktop](../../../docs/framework/resources/index.md)
